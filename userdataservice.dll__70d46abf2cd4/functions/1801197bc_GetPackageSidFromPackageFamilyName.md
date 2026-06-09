# GetPackageSidFromPackageFamilyName

- ea: `0x1801197bc`
- end: `0x180119ad3`
- name: `GetPackageSidFromPackageFamilyName`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180118d80`

## callees

- `0x180035c40`
- `0x180042d18`
- `0x180064880`
- `0x1801197bc`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119980`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801199a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801199ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119a3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119980`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801199a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801199ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119a3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801199b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801199b1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18011981d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801198c3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18011981d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801198c3`

## pseudocode

```c
__int64 __fastcall GetPackageSidFromPackageFamilyName(const WCHAR *a1, __int64 a2)
{
  int ActivationFactory; // eax
  __int64 v4; // rcx
  int v5; // ebx
  void (*v6)(void); // rax
  __int64 v8; // rcx
  void (*v9)(void); // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  void (*v12)(void); // rax
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // [rsp+30h] [rbp-19h] BYREF
  __int64 v31; // [rsp+38h] [rbp-11h] BYREF
  __int64 v32; // [rsp+40h] [rbp-9h] BYREF
  __int64 v33; // [rsp+48h] [rbp-1h] BYREF
  HSTRING string; // [rsp+50h] [rbp+7h] BYREF
  const WCHAR *v35; // [rsp+58h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+17h] BYREF
  __int64 v37; // [rsp+78h] [rbp+2Fh]

  v35 = a1;
  v30 = 0;
  v37 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.User",
    0x26u,
    0x25u);
  ActivationFactory = RoGetActivationFactory(v37, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v30);
  v4 = v30;
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    if ( !v30 )
      return (unsigned int)v5;
    v30 = 0;
    v6 = *(void (**)(void))(*(_QWORD *)v4 + 16LL);
LABEL_4:
    v6();
    return (unsigned int)v5;
  }
  v31 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 104LL))(v30, &v31);
  if ( v5 < 0 )
  {
    v8 = v31;
    if ( !v31 )
    {
LABEL_10:
      v10 = v30;
      if ( !v30 )
        return (unsigned int)v5;
      v30 = 0;
      v6 = *(void (**)(void))(*(_QWORD *)v10 + 16LL);
      goto LABEL_4;
    }
    v31 = 0;
    v9 = *(void (**)(void))(*(_QWORD *)v8 + 16LL);
LABEL_9:
    v9();
    goto LABEL_10;
  }
  v32 = 0;
  v37 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.PackageFamily",
    0x2Fu,
    0x2Eu);
  v5 = RoGetActivationFactory(v37, &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426, &v32);
  if ( v5 < 0 )
  {
    v11 = v32;
    if ( !v32 )
    {
LABEL_16:
      v13 = v31;
      if ( !v31 )
        goto LABEL_10;
      v31 = 0;
      v9 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
      goto LABEL_9;
    }
    v32 = 0;
    v12 = *(void (**)(void))(*(_QWORD *)v11 + 16LL);
LABEL_15:
    v12();
    goto LABEL_16;
  }
  v14 = v32;
  v33 = 0;
  v15 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, __int64 *))(*(_QWORD *)v32 + 192LL);
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v35);
  v5 = v15(v14, v31, v16[1].Reserved.Reserved1, &v33);
  if ( v5 < 0 )
  {
LABEL_19:
    v17 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v32;
    if ( !v32 )
      goto LABEL_16;
    v32 = 0;
    v12 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
    goto LABEL_15;
  }
  v19 = v33;
  string = 0;
  v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v20(v19, &string);
  if ( v5 < 0 )
  {
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_19;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          a2,
                          StringRawBuffer) )
  {
    WindowsDeleteString(string);
    v26 = v33;
    string = 0;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    return 0;
  }
  else
  {
    WindowsDeleteString(string);
    v22 = v33;
    string = 0;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1801197bc  mov     [rsp-8+arg_10], rbx
0x1801197c1  mov     [rsp-8+arg_18], rsi
0x1801197c6  push    rbp
0x1801197c7  push    rdi
0x1801197c8  push    r14
0x1801197ca  lea     rbp, [rsp-47h]
0x1801197cf  sub     rsp, 90h
0x1801197d6  mov     rax, cs:__security_cookie
0x1801197dd  xor     rax, rsp
0x1801197e0  mov     [rbp+57h+var_20], rax
0x1801197e4  xor     r14d, r14d
0x1801197e7  mov     [rbp+57h+var_48], rcx
0x1801197eb  mov     rsi, rdx
0x1801197ee  mov     [rbp+57h+var_70], r14
0x1801197f2  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x1801197f9  mov     [rbp+57h+var_28], r14
0x1801197fd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180119801  lea     r9d, [r14+25h]; unsigned int
0x180119805  lea     r8d, [r14+26h]; unsigned int
0x180119809  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18011980e  mov     rcx, [rbp+57h+var_28]
0x180119812  lea     r8, [rbp+57h+var_70]
0x180119816  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x18011981d  call    cs:__imp_RoGetActivationFactory
0x180119823  mov     rcx, [rbp+57h+var_70]
0x180119827  mov     ebx, eax
0x180119829  test    eax, eax
0x18011982b  jns     short loc_180119849
0x18011982d  test    rcx, rcx
0x180119830  jz      short loc_180119842
0x180119832  mov     [rbp+57h+var_70], r14
0x180119836  mov     rdx, [rcx]
0x180119839  mov     rax, [rdx+10h]
0x18011983d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119842  mov     eax, ebx
0x180119844  jmp     loc_180119AAF
0x180119849  mov     [rbp+57h+var_68], r14
0x18011984d  lea     rdx, [rbp+57h+var_68]
0x180119851  mov     rax, [rcx]
0x180119854  mov     rax, [rax+68h]
0x180119858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011985d  mov     ebx, eax
0x18011985f  test    eax, eax
0x180119861  jns     short loc_180119892
0x180119863  mov     rcx, [rbp+57h+var_68]
0x180119867  test    rcx, rcx
0x18011986a  jz      short loc_18011987C
0x18011986c  mov     [rbp+57h+var_68], r14
0x180119870  mov     rdx, [rcx]
0x180119873  mov     rax, [rdx+10h]
0x180119877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011987c  mov     rcx, [rbp+57h+var_70]
0x180119880  test    rcx, rcx
0x180119883  jz      short loc_180119842
0x180119885  mov     [rbp+57h+var_70], r14
0x180119889  mov     rax, [rcx]
0x18011988c  mov     rax, [rax+10h]
0x180119890  jmp     short loc_18011983D
0x180119892  mov     r9d, 2Eh ; '.'; unsigned int
0x180119898  mov     [rbp+57h+var_60], r14
0x18011989c  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1801198a3  mov     [rbp+57h+var_28], r14
0x1801198a7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801198ab  lea     r8d, [r9+1]; unsigned int
0x1801198af  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801198b4  mov     rcx, [rbp+57h+var_28]
0x1801198b8  lea     r8, [rbp+57h+var_60]
0x1801198bc  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x1801198c3  call    cs:__imp_RoGetActivationFactory
0x1801198c9  mov     ebx, eax
0x1801198cb  test    eax, eax
0x1801198cd  jns     short loc_180119901
0x1801198cf  mov     rcx, [rbp+57h+var_60]
0x1801198d3  test    rcx, rcx
0x1801198d6  jz      short loc_1801198E8
0x1801198d8  mov     [rbp+57h+var_60], r14
0x1801198dc  mov     rdx, [rcx]
0x1801198df  mov     rax, [rdx+10h]
0x1801198e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801198e8  mov     rcx, [rbp+57h+var_68]
0x1801198ec  test    rcx, rcx
0x1801198ef  jz      short loc_18011987C
0x1801198f1  mov     [rbp+57h+var_68], r14
0x1801198f5  mov     rax, [rcx]
0x1801198f8  mov     rax, [rax+10h]
0x1801198fc  jmp     loc_180119877
0x180119901  mov     rdi, [rbp+57h+var_60]
0x180119905  lea     rdx, [rbp+57h+var_48]
0x180119909  mov     [rbp+57h+var_58], r14
0x18011990d  lea     rcx, [rbp+57h+hstringHeader]
0x180119911  mov     rax, [rdi]
0x180119914  mov     rbx, [rax+0C0h]
0x18011991b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180119920  mov     rdx, [rbp+57h+var_68]
0x180119924  lea     r9, [rbp+57h+var_58]
0x180119928  mov     rcx, rdi
0x18011992b  mov     r8, [rax+18h]
0x18011992f  mov     rax, rbx
0x180119932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119937  mov     ebx, eax
0x180119939  test    eax, eax
0x18011993b  jns     short loc_18011996F
0x18011993d  mov     rcx, [rbp+57h+var_58]
0x180119941  test    rcx, rcx
0x180119944  jz      short loc_180119956
0x180119946  mov     [rbp+57h+var_58], r14
0x18011994a  mov     rdx, [rcx]
0x18011994d  mov     rax, [rdx+10h]
0x180119951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119956  mov     rcx, [rbp+57h+var_60]
0x18011995a  test    rcx, rcx
0x18011995d  jz      short loc_1801198E8
0x18011995f  mov     [rbp+57h+var_60], r14
0x180119963  mov     rax, [rcx]
0x180119966  mov     rax, [rax+10h]
0x18011996a  jmp     loc_1801198E3
0x18011996f  mov     rdi, [rbp+57h+var_58]
0x180119973  xor     ecx, ecx; string
0x180119975  mov     [rbp+57h+string], r14
0x180119979  mov     rax, [rdi]
0x18011997c  mov     rbx, [rax+60h]
0x180119980  call    cs:__imp_WindowsDeleteString
0x180119986  lea     rdx, [rbp+57h+string]
0x18011998a  mov     [rbp+57h+string], r14
0x18011998e  mov     rcx, rdi
0x180119991  mov     rax, rbx
0x180119994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119999  mov     rcx, [rbp+57h+string]; string
0x18011999d  mov     ebx, eax
0x18011999f  test    eax, eax
0x1801199a1  jns     short loc_1801199AF
0x1801199a3  call    cs:__imp_WindowsDeleteString
0x1801199a9  mov     [rbp+57h+string], r14
0x1801199ad  jmp     short loc_18011993D
0x1801199af  xor     edx, edx; length
0x1801199b1  call    cs:__imp_WindowsGetStringRawBuffer
0x1801199b7  mov     rdx, rax
0x1801199ba  mov     rcx, rsi
0x1801199bd  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1801199c2  mov     rcx, [rbp+57h+string]; string
0x1801199c6  test    al, al
0x1801199c8  jnz     short loc_180119A3F
0x1801199ca  call    cs:__imp_WindowsDeleteString
0x1801199d0  mov     rcx, [rbp+57h+var_58]
0x1801199d4  mov     [rbp+57h+string], r14
0x1801199d8  test    rcx, rcx
0x1801199db  jz      short loc_1801199ED
0x1801199dd  mov     [rbp+57h+var_58], r14
0x1801199e1  mov     rax, [rcx]
0x1801199e4  mov     rax, [rax+10h]
0x1801199e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801199ed  mov     rcx, [rbp+57h+var_60]
0x1801199f1  test    rcx, rcx
0x1801199f4  jz      short loc_180119A06
0x1801199f6  mov     [rbp+57h+var_60], r14
0x1801199fa  mov     rax, [rcx]
0x1801199fd  mov     rax, [rax+10h]
0x180119a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119a06  mov     rcx, [rbp+57h+var_68]
0x180119a0a  test    rcx, rcx
0x180119a0d  jz      short loc_180119A1F
0x180119a0f  mov     [rbp+57h+var_68], r14
0x180119a13  mov     rax, [rcx]
0x180119a16  mov     rax, [rax+10h]
0x180119a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119a1f  mov     rcx, [rbp+57h+var_70]
0x180119a23  test    rcx, rcx
0x180119a26  jz      short loc_180119A38
0x180119a28  mov     [rbp+57h+var_70], r14
0x180119a2c  mov     rax, [rcx]
0x180119a2f  mov     rax, [rax+10h]
0x180119a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119a38  mov     eax, 8007000Eh
0x180119a3d  jmp     short loc_180119AAF
0x180119a3f  call    cs:__imp_WindowsDeleteString
0x180119a45  mov     rcx, [rbp+57h+var_58]
0x180119a49  mov     [rbp+57h+string], r14
0x180119a4d  test    rcx, rcx
0x180119a50  jz      short loc_180119A62
0x180119a52  mov     [rbp+57h+var_58], r14
0x180119a56  mov     rax, [rcx]
0x180119a59  mov     rax, [rax+10h]
0x180119a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119a62  mov     rcx, [rbp+57h+var_60]
0x180119a66  test    rcx, rcx
0x180119a69  jz      short loc_180119A7B
0x180119a6b  mov     [rbp+57h+var_60], r14
0x180119a6f  mov     rax, [rcx]
0x180119a72  mov     rax, [rax+10h]
0x180119a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119a7b  mov     rcx, [rbp+57h+var_68]
0x180119a7f  test    rcx, rcx
0x180119a82  jz      short loc_180119A94
0x180119a84  mov     [rbp+57h+var_68], r14
0x180119a88  mov     rax, [rcx]
0x180119a8b  mov     rax, [rax+10h]
0x180119a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119a94  mov     rcx, [rbp+57h+var_70]
0x180119a98  test    rcx, rcx
0x180119a9b  jz      short loc_180119AAD
0x180119a9d  mov     [rbp+57h+var_70], r14
0x180119aa1  mov     rax, [rcx]
0x180119aa4  mov     rax, [rax+10h]
0x180119aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119aad  xor     eax, eax
0x180119aaf  mov     rcx, [rbp+57h+var_20]
0x180119ab3  xor     rcx, rsp; StackCookie
0x180119ab6  call    __security_check_cookie
0x180119abb  lea     r11, [rsp+0A0h+var_10]
0x180119ac3  mov     rbx, [r11+30h]
0x180119ac7  mov     rsi, [r11+38h]
0x180119acb  mov     rsp, r11
0x180119ace  pop     r14
0x180119ad0  pop     rdi
0x180119ad1  pop     rbp
0x180119ad2  retn
```
