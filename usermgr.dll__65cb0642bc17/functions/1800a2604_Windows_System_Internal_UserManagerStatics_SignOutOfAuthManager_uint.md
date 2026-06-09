# Windows::System::Internal::UserManagerStatics::SignOutOfAuthManager(uint)

- ea: `0x1800a2604`
- end: `0x1800a287a`
- name: `?SignOutOfAuthManager@UserManagerStatics@Internal@System@Windows@@AEAAJI@Z`
- size: `630`
- prototype: `int(Windows::System::Internal::UserManagerStatics *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180061f98`
- `0x18008ceac`
- `0x1800a1dd4`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x18000ed00`
- `0x180092d74`
- `0x1800a2604`
- `0x1800ec010`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800a27d6`
- `msvcrt!wcsstr` at `0x1800a27fb`
- `msvcrt!wcsstr` at `0x1800a27d6`
- `msvcrt!wcsstr` at `0x1800a27fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a26f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a27c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a27eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a281b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a26f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a27c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a27eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a281b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a26cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a286d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a26cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a2793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a286d`

## string_xrefs

- `0x1800a26b4`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a2844`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::UserManagerStatics::SignOutOfAuthManager(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2)
{
  char *v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  Windows::System::Internal::UserManagerStatics *v8; // rcx
  int SponsoredUserName; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, PCWSTR, _QWORD); // rbx
  PCWSTR v13; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, int *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  const wchar_t *StringRawBuffer; // rax
  const wchar_t *v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, PCWSTR, _QWORD); // rbx
  PCWSTR v23; // rax
  int v24[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HSTRING string; // [rsp+50h] [rbp+20h] BYREF
  HSTRING v27; // [rsp+60h] [rbp+30h] BYREF
  __int64 v28; // [rsp+68h] [rbp+38h] BYREF

  v4 = (char *)this + 552;
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 69) + 8LL))((char *)this + 552) )
    return 0;
  v27 = 0;
  v28 = 0;
  *(_QWORD *)v24 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v5 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
         v4,
         &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
         &v28);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 5970;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v5,
      v24[0]);
    goto LABEL_22;
  }
  if ( a2 - 1 > 0xE )
  {
    v15 = *((_QWORD *)this + 67);
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v15 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
    v5 = v16(v15, a2, v24);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 5980;
      goto LABEL_21;
    }
    v17 = *(_QWORD *)v24;
    v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v24 + 64LL);
    WindowsDeleteString(v27);
    v27 = 0;
    v5 = v18(v17, &v27);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 5981;
      goto LABEL_21;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v27, 0);
    if ( wcsstr(StringRawBuffer, L"@") )
    {
      v20 = WindowsGetStringRawBuffer(v27, 0);
      if ( !wcsstr(v20, L"\\") )
      {
        v21 = v28;
        v22 = *(__int64 (__fastcall **)(__int64, PCWSTR, _QWORD))(*(_QWORD *)v28 + 80LL);
        v23 = WindowsGetStringRawBuffer(v27, 0);
        v5 = v22(v21, v23, 0);
        v6 = v5;
        if ( v5 < 0 )
        {
          v7 = 5985;
          goto LABEL_21;
        }
      }
    }
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    WindowsDeleteString(v27);
    return 0;
  }
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  SponsoredUserName = Windows::System::Internal::UserManagerStatics::GetSponsoredUserName(v8, a2, &string);
  v6 = SponsoredUserName;
  if ( SponsoredUserName >= 0 )
  {
    v11 = v28;
    v12 = *(__int64 (__fastcall **)(__int64, PCWSTR, _QWORD))(*(_QWORD *)v28 + 80LL);
    v13 = WindowsGetStringRawBuffer(string, 0);
    SponsoredUserName = v12(v11, v13, 0);
    v6 = SponsoredUserName;
    if ( SponsoredUserName < 0 )
    {
      v10 = 5976;
      goto LABEL_7;
    }
    WindowsDeleteString(string);
    goto LABEL_11;
  }
  v10 = 5975;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
    (const char *)(unsigned int)SponsoredUserName,
    v24[0]);
  WindowsDeleteString(string);
  string = 0;
LABEL_22:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  WindowsDeleteString(v27);
  return v6;
}

```

## disassembly

```asm
0x1800a2604  mov     [rsp-18h+arg_8], rbx
0x1800a2609  push    rbp
0x1800a260a  push    rsi
0x1800a260b  push    rdi
0x1800a260c  mov     rbp, rsp
0x1800a260f  sub     rsp, 30h
0x1800a2613  mov     esi, edx
0x1800a2615  mov     rdi, rcx
0x1800a2618  lea     rbx, [rcx+228h]
0x1800a261f  mov     rax, [rbx]
0x1800a2622  mov     rcx, rbx
0x1800a2625  mov     rax, [rax+8]
0x1800a2629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a262e  test    al, al
0x1800a2630  jz      loc_1800A273D
0x1800a2636  mov     [rbp+arg_10], 0
0x1800a263e  mov     [rbp+arg_18], 0
0x1800a2646  mov     qword ptr [rbp+var_10], 0
0x1800a264e  lea     rcx, [rbp+arg_18]
0x1800a2652  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2657  lea     r8, [rbp+arg_18]
0x1800a265b  lea     rdx, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5
0x1800a2662  mov     rcx, rbx
0x1800a2665  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x1800a266a  mov     ebx, eax
0x1800a266c  test    eax, eax
0x1800a266e  jns     short loc_1800A267A
0x1800a2670  mov     edx, 1752h
0x1800a2675  jmp     loc_1800A2841
0x1800a267a  lea     eax, [rsi-1]
0x1800a267d  cmp     eax, 0Eh
0x1800a2680  ja      loc_1800A274C
0x1800a2686  mov     [rbp+string], 0
0x1800a268e  xor     ecx, ecx; string
0x1800a2690  call    cs:__imp_WindowsDeleteString
0x1800a2696  mov     [rbp+string], 0
0x1800a269e  lea     r8, [rbp+string]; HSTRING *
0x1800a26a2  mov     edx, esi; unsigned int
0x1800a26a4  call    ?GetSponsoredUserName@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserManagerStatics::GetSponsoredUserName(uint,HSTRING__ * *)
0x1800a26a9  mov     ebx, eax
0x1800a26ab  test    eax, eax
0x1800a26ad  jns     short loc_1800A26DF
0x1800a26af  mov     edx, 1757h; void *
0x1800a26b4  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800a26bb  mov     r9d, eax; char *
0x1800a26be  mov     rcx, [rbp+18h]; this
0x1800a26c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a26c7  nop
0x1800a26c8  mov     rcx, [rbp+string]; string
0x1800a26cc  call    cs:__imp_WindowsDeleteString
0x1800a26d2  mov     [rbp+string], 0
0x1800a26da  jmp     loc_1800A2855
0x1800a26df  mov     rdi, [rbp+arg_18]
0x1800a26e3  mov     rax, [rdi]
0x1800a26e6  mov     rbx, [rax+50h]
0x1800a26ea  xor     edx, edx; length
0x1800a26ec  mov     rcx, [rbp+string]; string
0x1800a26f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a26f6  xor     r8d, r8d
0x1800a26f9  mov     rdx, rax
0x1800a26fc  mov     rcx, rdi
0x1800a26ff  mov     rax, rbx
0x1800a2702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2707  mov     ebx, eax
0x1800a2709  test    eax, eax
0x1800a270b  jns     short loc_1800A2714
0x1800a270d  mov     edx, 1758h
0x1800a2712  jmp     short loc_1800A26B4
0x1800a2714  mov     rcx, [rbp+string]; string
0x1800a2718  call    cs:__imp_WindowsDeleteString
0x1800a271e  nop
0x1800a271f  lea     rcx, [rbp+var_10]
0x1800a2723  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2728  nop
0x1800a2729  lea     rcx, [rbp+arg_18]
0x1800a272d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2732  nop
0x1800a2733  mov     rcx, [rbp+arg_10]; string
0x1800a2737  call    cs:__imp_WindowsDeleteString
0x1800a273d  xor     eax, eax
0x1800a273f  mov     rbx, [rsp+30h+arg_8]
0x1800a2744  add     rsp, 30h
0x1800a2748  pop     rdi
0x1800a2749  pop     rsi
0x1800a274a  pop     rbp
0x1800a274b  retn
0x1800a274c  mov     rdi, [rdi+218h]
0x1800a2753  mov     rax, [rdi]
0x1800a2756  mov     rbx, [rax+60h]
0x1800a275a  lea     rcx, [rbp+var_10]
0x1800a275e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2763  lea     r8, [rbp+var_10]
0x1800a2767  mov     edx, esi
0x1800a2769  mov     rcx, rdi
0x1800a276c  mov     rax, rbx
0x1800a276f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2774  mov     ebx, eax
0x1800a2776  test    eax, eax
0x1800a2778  jns     short loc_1800A2784
0x1800a277a  mov     edx, 175Ch
0x1800a277f  jmp     loc_1800A2841
0x1800a2784  mov     rdi, qword ptr [rbp+var_10]
0x1800a2788  mov     rax, [rdi]
0x1800a278b  mov     rbx, [rax+40h]
0x1800a278f  mov     rcx, [rbp+arg_10]; string
0x1800a2793  call    cs:__imp_WindowsDeleteString
0x1800a2799  mov     [rbp+arg_10], 0
0x1800a27a1  lea     rdx, [rbp+arg_10]
0x1800a27a5  mov     rcx, rdi
0x1800a27a8  mov     rax, rbx
0x1800a27ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a27b0  mov     ebx, eax
0x1800a27b2  test    eax, eax
0x1800a27b4  jns     short loc_1800A27C0
0x1800a27b6  mov     edx, 175Dh
0x1800a27bb  jmp     loc_1800A2841
0x1800a27c0  xor     edx, edx; length
0x1800a27c2  mov     rcx, [rbp+arg_10]; string
0x1800a27c6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a27cc  lea     rdx, asc_1801118C4; "@"
0x1800a27d3  mov     rcx, rax; Str
0x1800a27d6  call    cs:__imp_wcsstr
0x1800a27dc  test    rax, rax
0x1800a27df  jz      loc_1800A271F
0x1800a27e5  xor     edx, edx; length
0x1800a27e7  mov     rcx, [rbp+arg_10]; string
0x1800a27eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a27f1  lea     rdx, SubStr; "\\"
0x1800a27f8  mov     rcx, rax; Str
0x1800a27fb  call    cs:__imp_wcsstr
0x1800a2801  test    rax, rax
0x1800a2804  jnz     loc_1800A271F
0x1800a280a  mov     rdi, [rbp+arg_18]
0x1800a280e  mov     rax, [rdi]
0x1800a2811  mov     rbx, [rax+50h]
0x1800a2815  xor     edx, edx; length
0x1800a2817  mov     rcx, [rbp+arg_10]; string
0x1800a281b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a2821  xor     r8d, r8d
0x1800a2824  mov     rdx, rax
0x1800a2827  mov     rcx, rdi
0x1800a282a  mov     rax, rbx
0x1800a282d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2832  mov     ebx, eax
0x1800a2834  test    eax, eax
0x1800a2836  jns     loc_1800A271F
0x1800a283c  mov     edx, 1761h; void *
0x1800a2841  mov     r9d, eax; char *
0x1800a2844  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800a284b  mov     rcx, [rbp+18h]; this
0x1800a284f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2854  nop
0x1800a2855  lea     rcx, [rbp+var_10]
0x1800a2859  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a285e  nop
0x1800a285f  lea     rcx, [rbp+arg_18]
0x1800a2863  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2868  nop
0x1800a2869  mov     rcx, [rbp+arg_10]; string
0x1800a286d  call    cs:__imp_WindowsDeleteString
0x1800a2873  mov     eax, ebx
0x1800a2875  jmp     loc_1800A273F
```
