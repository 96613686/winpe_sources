# DeSerializePropertiesForExtension(Windows::Foundation::Collections::IPropertySet *,Windows::System::Internal::Launch::ExtensionProperties &)

- ea: `0x1800252f8`
- end: `0x180025837`
- name: `?DeSerializePropertiesForExtension@@YAJPEAUIPropertySet@Collections@Foundation@Windows@@AEAVExtensionProperties@Launch@Internal@System@4@@Z`
- size: `1343`
- prototype: `__int64 __fastcall(struct Windows::Foundation::Collections::IPropertySet *, struct Windows::System::Internal::Launch::ExtensionProperties *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024abc`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180023044`
- `0x1800252f8`
- `0x18002cec0`
- `0x180034ba0`
- `0x18003fe38`
- `0x1800596d8`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025422`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800254b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025593`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002581a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025830`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025422`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800254b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025593`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002581a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025830`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002571f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002574f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002577b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800257a7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002571f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002574f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002577b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800257a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800256fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800256fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800255a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800256c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800255a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800256c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002540c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800254a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002540c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800254a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DeSerializePropertiesForExtension(
        __int64 (__fastcall ***a1)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **),
        HSTRING *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 *v7; // rcx
  __int64 *v9; // rdi
  __int64 v10; // r15
  __int64 v11; // r13
  unsigned __int64 v12; // rbx
  unsigned int v13; // eax
  UINT32 v14; // edx
  HRESULT v15; // eax
  __int64 *v16; // rdi
  unsigned __int64 v17; // rbx
  unsigned int v18; // eax
  UINT32 v19; // edx
  HRESULT v20; // eax
  __int64 *v21; // rdi
  __int64 (__fastcall *v22)(__int64 *, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v23; // rax
  int v24; // eax
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rbx
  int v27; // eax
  unsigned __int64 v28; // rbx
  unsigned int v29; // eax
  int ElementAttribute; // eax
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 *v33; // rcx
  HSTRING_HEADER *v34; // rax
  int v35; // eax
  const WCHAR *StringRawBuffer; // rbx
  __int64 *v37; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-60h]
  char v39[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-48h] BYREF
  __int64 *v41; // [rsp+40h] [rbp-40h] BYREF
  __int64 v42; // [rsp+48h] [rbp-38h] BYREF
  HSTRING v43; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v41 = 0;
  v4 = **a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  v5 = v4((struct Windows::Foundation::Collections::IPropertySet *)a1, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v41);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
    v7 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64 *))(*v7 + 16))(v7);
    }
    return v6;
  }
  v40 = 0;
  v9 = v41;
  v10 = *v41;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  string = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( aProtocol[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
LABEL_58:
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180025836LL);
  }
  v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
  v14 = v13 - 1;
  if ( (unsigned int)v12 < v13 )
    v14 = v12;
  v15 = WindowsCreateStringReference(L"Protocol", v14, &hstringHeader, &string);
  if ( v15 < 0 )
    RaiseException(v15, 1u, 0, 0);
  if ( (*(int (__fastcall **)(__int64 *, HSTRING, _QWORD))(v10 + 48))(v9, string, &v40) < 0 )
  {
    v16 = v41;
    v11 = *v41;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    string = 0;
    v17 = -1;
    do
      ++v17;
    while ( aFiletypeassoci_0[v17] );
    if ( v17 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      goto LABEL_28;
    }
    v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v17);
    v19 = v18 - 1;
    if ( (unsigned int)v17 < v18 )
      v19 = v17;
    v20 = WindowsCreateStringReference(L"FileTypeAssociation", v19, &hstringHeader, &string);
    if ( v20 < 0 )
      RaiseException(v20, 1u, 0, 0);
    if ( (*(int (__fastcall **)(__int64 *, HSTRING, _QWORD))(v11 + 48))(v16, string, &v40) < 0 )
    {
      v21 = v41;
      v22 = *(__int64 (__fastcall **)(__int64 *, PVOID, _QWORD))(*v41 + 48);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&off_180112FF0);
      v24 = v22(v21, v23[1].Reserved.Reserved1, &v40);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x111,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
          (const char *)(unsigned int)v24,
          bIgnoreCase);
    }
    v11 = -1;
  }
  v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
  if ( !v40 )
    goto LABEL_52;
  v42 = 0;
  v26 = **v40;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v27 = v26(v25, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v42);
  v6 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v27,
      bIgnoreCase);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    return v6;
  }
LABEL_28:
  WindowsDeleteString(a2[5]);
  a2[5] = 0;
  string = 0;
  v28 = v11;
  do
    ++v28;
  while ( aParameters_0[v28] );
  if ( v28 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_58;
  }
  v29 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v28);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@Parameters", v29, v28);
  ElementAttribute = TryGetElementAttribute(v42, string, a2 + 5, v39);
  v6 = ElementAttribute;
  if ( ElementAttribute < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)ElementAttribute,
      bIgnoreCase);
    v31 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
    if ( v40 )
    {
      v40 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v32)[2])(v32);
    }
    v33 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    }
    return v6;
  }
  v39[0] = 0;
  WindowsDeleteString(0);
  v43 = 0;
  v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)off_1801230C8);
  v35 = TryGetElementAttribute(v42, v34[1].Reserved.Reserved1, &v43, v39);
  v6 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v35,
      bIgnoreCase);
    WindowsDeleteString(v43);
    goto LABEL_41;
  }
  if ( v39[0] )
  {
    *((_DWORD *)a2 + 12) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v43, 0);
    if ( CompareStringOrdinal(StringRawBuffer, v11, L"useHalf", v11, 1) == 2 )
    {
      *((_DWORD *)a2 + 12) = 2;
    }
    else if ( CompareStringOrdinal(StringRawBuffer, v11, L"useLess", v11, 1) == 2 )
    {
      *((_DWORD *)a2 + 12) = 1;
    }
    else if ( CompareStringOrdinal(StringRawBuffer, v11, L"useMinimum", v11, 1) == 2 )
    {
      *((_DWORD *)a2 + 12) = 4;
    }
    else if ( CompareStringOrdinal(StringRawBuffer, v11, L"useMore", v11, 1) == 2 )
    {
      *((_DWORD *)a2 + 12) = 3;
    }
  }
  WindowsDeleteString(v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
LABEL_52:
  if ( v25 )
  {
    v40 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v25)[2])(v25);
  }
  v37 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
  }
  return 0;
}

```

## disassembly

```asm
0x1800252f8  mov     [rsp-38h+arg_10], rbx
0x1800252fd  push    rbp
0x1800252fe  push    rsi
0x1800252ff  push    rdi
0x180025300  push    r12
0x180025302  push    r13
0x180025304  push    r14
0x180025306  push    r15
0x180025308  mov     rbp, rsp
0x18002530b  sub     rsp, 80h
0x180025312  mov     rax, cs:__security_cookie
0x180025319  xor     rax, rsp
0x18002531c  mov     [rbp+var_8], rax
0x180025320  mov     r14, rdx
0x180025323  mov     rdi, rcx
0x180025326  xor     r12d, r12d
0x180025329  mov     [rbp+var_40], r12
0x18002532d  mov     rax, [rcx]
0x180025330  mov     rbx, [rax]
0x180025333  lea     rcx, [rbp+var_40]
0x180025337  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002533c  lea     r8, [rbp+var_40]
0x180025340  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180025347  mov     rcx, rdi
0x18002534a  mov     rax, rbx
0x18002534d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025352  mov     ebx, eax
0x180025354  test    eax, eax
0x180025356  jns     short loc_1800253B4
0x180025358  mov     rcx, [rbp+38h]; this
0x18002535c  mov     r9d, eax; char *
0x18002535f  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180025366  mov     edx, 10Ah; void *
0x18002536b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025370  nop
0x180025371  mov     rcx, [rbp+var_40]
0x180025375  test    rcx, rcx
0x180025378  jz      short loc_18002538B
0x18002537a  mov     [rbp+var_40], r12
0x18002537e  mov     rax, [rcx]
0x180025381  mov     rax, [rax+10h]
0x180025385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002538a  nop
0x18002538b  mov     eax, ebx
0x18002538d  mov     rcx, [rbp+var_8]
0x180025391  xor     rcx, rsp; StackCookie
0x180025394  call    __security_check_cookie
0x180025399  mov     rbx, [rsp+80h+arg_10]
0x1800253a1  add     rsp, 80h
0x1800253a8  pop     r15
0x1800253aa  pop     r14
0x1800253ac  pop     r13
0x1800253ae  pop     r12
0x1800253b0  pop     rdi
0x1800253b1  pop     rsi
0x1800253b2  pop     rbp
0x1800253b3  retn
0x1800253b4  mov     [rbp+var_48], r12
0x1800253b8  mov     rdi, [rbp+var_40]
0x1800253bc  mov     r15, [rdi]
0x1800253bf  lea     rcx, [rbp+var_48]
0x1800253c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800253c8  mov     [rbp+string], r12
0x1800253cc  mov     rsi, cs:off_180112DF0; "Protocol"
0x1800253d3  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800253d7  mov     rbx, r13
0x1800253da  inc     rbx
0x1800253dd  cmp     [rsi+rbx*2], r12w
0x1800253e2  jnz     short loc_1800253DA
0x1800253e4  mov     eax, 0FFFFFFFFh
0x1800253e9  cmp     rbx, rax
0x1800253ec  ja      loc_180025821
0x1800253f2  mov     ecx, ebx; unsigned int
0x1800253f4  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800253f9  lea     edx, [rax-1]
0x1800253fc  cmp     ebx, eax
0x1800253fe  cmovb   edx, ebx; length
0x180025401  lea     r9, [rbp+string]; string
0x180025405  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180025409  mov     rcx, rsi; sourceString
0x18002540c  call    cs:__imp_WindowsCreateStringReference
0x180025412  test    eax, eax
0x180025414  jns     short loc_180025429
0x180025416  xor     r9d, r9d; lpArguments
0x180025419  xor     r8d, r8d; nNumberOfArguments
0x18002541c  lea     edx, [r9+1]; dwExceptionFlags
0x180025420  mov     ecx, eax; dwExceptionCode
0x180025422  call    cs:__imp_RaiseException
0x180025428  nop
0x180025429  lea     r8, [rbp+var_48]
0x18002542d  mov     rdx, [rbp+string]
0x180025431  mov     rcx, rdi
0x180025434  mov     rax, [r15+30h]
0x180025438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002543d  nop
0x18002543e  shr     eax, 1Fh
0x180025441  lea     rsi, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180025448  test    al, al
0x18002544a  jz      loc_18002552F
0x180025450  mov     rdi, [rbp+var_40]
0x180025454  mov     r13, [rdi]
0x180025457  lea     rcx, [rbp+var_48]
0x18002545b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025460  mov     [rbp+string], r12
0x180025464  mov     r15, cs:off_180112E38; "FileTypeAssociation"
0x18002546b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002546f  inc     rbx
0x180025472  cmp     [r15+rbx*2], r12w
0x180025477  jnz     short loc_18002546F
0x180025479  mov     eax, 0FFFFFFFFh
0x18002547e  cmp     rbx, rax
0x180025481  ja      loc_180025584
0x180025487  mov     ecx, ebx; unsigned int
0x180025489  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002548e  lea     edx, [rax-1]
0x180025491  cmp     ebx, eax
0x180025493  cmovb   edx, ebx; length
0x180025496  lea     r9, [rbp+string]; string
0x18002549a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002549e  mov     rcx, r15; sourceString
0x1800254a1  call    cs:__imp_WindowsCreateStringReference
0x1800254a7  test    eax, eax
0x1800254a9  jns     short loc_1800254BE
0x1800254ab  xor     r9d, r9d; lpArguments
0x1800254ae  xor     r8d, r8d; nNumberOfArguments
0x1800254b1  lea     edx, [r9+1]; dwExceptionFlags
0x1800254b5  mov     ecx, eax; dwExceptionCode
0x1800254b7  call    cs:__imp_RaiseException
0x1800254bd  nop
0x1800254be  lea     r8, [rbp+var_48]
0x1800254c2  mov     rdx, [rbp+string]
0x1800254c6  mov     rcx, rdi
0x1800254c9  mov     rax, [r13+30h]
0x1800254cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254d2  nop
0x1800254d3  shr     eax, 1Fh
0x1800254d6  test    al, al
0x1800254d8  jz      short loc_18002552B
0x1800254da  mov     rdi, [rbp+var_40]
0x1800254de  mov     rax, [rdi]
0x1800254e1  mov     rbx, [rax+30h]
0x1800254e5  lea     rcx, [rbp+var_48]
0x1800254e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800254ee  lea     rdx, off_180112FF0; "AppUriHandler"
0x1800254f5  lea     rcx, [rbp+hstringHeader]
0x1800254f9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800254fe  nop
0x1800254ff  lea     r8, [rbp+var_48]
0x180025503  mov     rdx, [rax+18h]
0x180025507  mov     rcx, rdi
0x18002550a  mov     rax, rbx
0x18002550d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025512  mov     rcx, [rbp+38h]; this
0x180025516  test    eax, eax
0x180025518  jns     short loc_18002552B
0x18002551a  mov     r9d, eax; char *
0x18002551d  mov     r8, rsi; unsigned int
0x180025520  mov     edx, 111h; void *
0x180025525  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002552a  nop
0x18002552b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002552f  mov     rdi, [rbp+var_48]
0x180025533  test    rdi, rdi
0x180025536  jz      loc_1800257D1
0x18002553c  mov     [rbp+var_38], r12
0x180025540  mov     rax, [rdi]
0x180025543  mov     rbx, [rax]
0x180025546  lea     rcx, [rbp+var_38]
0x18002554a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002554f  lea     r8, [rbp+var_38]
0x180025553  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18002555a  mov     rcx, rdi
0x18002555d  mov     rax, rbx
0x180025560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025565  mov     ebx, eax
0x180025567  test    eax, eax
0x180025569  jns     short loc_18002559A
0x18002556b  mov     rcx, [rbp+38h]; this
0x18002556f  mov     r9d, eax; char *
0x180025572  mov     r8, rsi; unsigned int
0x180025575  mov     edx, 118h; void *
0x18002557a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002557f  jmp     loc_1800256C8
0x180025584  xor     r9d, r9d; lpArguments
0x180025587  xor     r8d, r8d; nNumberOfArguments
0x18002558a  lea     edx, [r9+1]; dwExceptionFlags
0x18002558e  mov     ecx, 80070216h; dwExceptionCode
0x180025593  call    cs:__imp_RaiseException
0x180025599  nop
0x18002559a  lea     rdi, [r14+28h]
0x18002559e  mov     rcx, [rdi]; string
0x1800255a1  call    cs:__imp_WindowsDeleteString
0x1800255a7  mov     [rdi], r12
0x1800255aa  mov     [rbp+string], r12
0x1800255ae  mov     r15, cs:off_180112F00; "@Parameters"
0x1800255b5  mov     rbx, r13
0x1800255b8  inc     rbx
0x1800255bb  cmp     [r15+rbx*2], r12w
0x1800255c0  jnz     short loc_1800255B8
0x1800255c2  mov     eax, 0FFFFFFFFh
0x1800255c7  cmp     rbx, rax
0x1800255ca  ja      loc_18002580B
0x1800255d0  mov     ecx, ebx; unsigned int
0x1800255d2  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800255d7  mov     r9d, ebx; unsigned int
0x1800255da  mov     r8d, eax; unsigned int
0x1800255dd  mov     rdx, r15; sourceString
0x1800255e0  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800255e4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800255e9  nop
0x1800255ea  lea     r9, [rbp+var_50]
0x1800255ee  mov     r8, rdi
0x1800255f1  mov     rdx, [rbp+string]
0x1800255f5  mov     rcx, [rbp+var_38]
0x1800255f9  call    ?TryGetElementAttribute@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAPEAU5@PEAE@Z; TryGetElementAttribute(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *,uchar *)
0x1800255fe  mov     ebx, eax
0x180025600  test    eax, eax
0x180025602  jns     short loc_18002566C
0x180025604  mov     rcx, [rbp+38h]; this
0x180025608  mov     r9d, eax; char *
0x18002560b  mov     r8, rsi; unsigned int
0x18002560e  mov     edx, 11Dh; void *
0x180025613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025618  nop
0x180025619  mov     rcx, [rbp+var_38]
0x18002561d  test    rcx, rcx
0x180025620  jz      short loc_180025633
0x180025622  mov     [rbp+var_38], r12
0x180025626  mov     rax, [rcx]
0x180025629  mov     rax, [rax+10h]
0x18002562d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025632  nop
0x180025633  mov     rcx, [rbp+var_48]
0x180025637  test    rcx, rcx
0x18002563a  jz      short loc_18002564D
0x18002563c  mov     [rbp+var_48], r12
0x180025640  mov     rax, [rcx]
0x180025643  mov     rax, [rax+10h]
0x180025647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002564c  nop
0x18002564d  mov     rcx, [rbp+var_40]
0x180025651  test    rcx, rcx
0x180025654  jz      short loc_180025667
0x180025656  mov     [rbp+var_40], r12
0x18002565a  mov     rax, [rcx]
0x18002565d  mov     rax, [rax+10h]
0x180025661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025666  nop
0x180025667  jmp     loc_18002538B
0x18002566c  mov     [rbp+var_50], r12b
0x180025670  xor     ecx, ecx; string
0x180025672  call    cs:__imp_WindowsDeleteString
0x180025678  mov     [rbp+var_30], r12
0x18002567c  lea     rdx, off_1801230C8; "@DesiredView"
0x180025683  lea     rcx, [rbp+hstringHeader]
0x180025687  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002568c  nop
0x18002568d  lea     r9, [rbp+var_50]
0x180025691  lea     r8, [rbp+var_30]
0x180025695  mov     rdx, [rax+18h]
0x180025699  mov     rcx, [rbp+var_38]
0x18002569d  call    ?TryGetElementAttribute@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAPEAU5@PEAE@Z; TryGetElementAttribute(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *,uchar *)
0x1800256a2  mov     ebx, eax
0x1800256a4  test    eax, eax
0x1800256a6  jns     short loc_1800256EA
0x1800256a8  mov     rcx, [rbp+38h]; this
0x1800256ac  mov     r9d, eax; char *
0x1800256af  mov     r8, rsi; unsigned int
0x1800256b2  mov     edx, 121h; void *
0x1800256b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800256bc  nop
0x1800256bd  mov     rcx, [rbp+var_30]; string
0x1800256c1  call    cs:__imp_WindowsDeleteString
0x1800256c7  nop
0x1800256c8  lea     rcx, [rbp+var_38]
0x1800256cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800256d1  nop
0x1800256d2  lea     rcx, [rbp+var_48]
0x1800256d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800256db  nop
0x1800256dc  lea     rcx, [rbp+var_40]
0x1800256e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800256e5  jmp     loc_18002538B
0x1800256ea  cmp     [rbp+var_50], r12b
0x1800256ee  jz      loc_1800257B9
0x1800256f4  mov     [r14+30h], r12d
0x1800256f8  xor     edx, edx; length
0x1800256fa  mov     rcx, [rbp+var_30]; string
0x1800256fe  call    cs:__imp_WindowsGetStringRawBuffer
0x180025704  mov     rbx, rax
0x180025707  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x18002570f  mov     r9d, r13d; cchCount2
0x180025712  lea     r8, aUsehalf; "useHalf"
0x180025719  mov     edx, r13d; cchCount1
0x18002571c  mov     rcx, rax; lpString1
0x18002571f  call    cs:__imp_CompareStringOrdinal
0x180025725  mov     edi, 2
0x18002572a  cmp     eax, edi
0x18002572c  jnz     short loc_180025737
0x18002572e  mov     [r14+30h], edi
  ... truncated ...
```
