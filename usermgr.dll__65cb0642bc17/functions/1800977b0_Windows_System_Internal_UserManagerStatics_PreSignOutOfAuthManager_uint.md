# Windows::System::Internal::UserManagerStatics::PreSignOutOfAuthManager(uint)

- ea: `0x1800977b0`
- end: `0x180097a26`
- name: `?PreSignOutOfAuthManager@UserManagerStatics@Internal@System@Windows@@AEAAJI@Z`
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
- `0x1800977b0`
- `0x1800ec010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180097982`
- `msvcrt!wcsstr` at `0x1800979a7`
- `msvcrt!wcsstr` at `0x180097982`
- `msvcrt!wcsstr` at `0x1800979a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009789f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097972`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800979ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009789f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097972`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180097997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800979ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009783c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800978c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800978e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009793f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097a19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009783c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800978c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800978e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009793f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097a19`

## string_xrefs

- `0x180097860`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800979f0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::System::Internal::UserManagerStatics::PreSignOutOfAuthManager(
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
  __int64 (__fastcall *v12)(__int64, PCWSTR); // rbx
  PCWSTR v13; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, int *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  const wchar_t *StringRawBuffer; // rax
  const wchar_t *v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, PCWSTR); // rbx
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
    v7 = 6003;
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
      v7 = 6013;
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
      v7 = 6014;
      goto LABEL_21;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v27, 0);
    if ( wcsstr(StringRawBuffer, L"@") )
    {
      v20 = WindowsGetStringRawBuffer(v27, 0);
      if ( !wcsstr(v20, L"\\") )
      {
        v21 = v28;
        v22 = *(__int64 (__fastcall **)(__int64, PCWSTR))(*(_QWORD *)v28 + 592LL);
        v23 = WindowsGetStringRawBuffer(v27, 0);
        v5 = v22(v21, v23);
        v6 = v5;
        if ( v5 < 0 )
        {
          v7 = 6019;
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
    v12 = *(__int64 (__fastcall **)(__int64, PCWSTR))(*(_QWORD *)v28 + 592LL);
    v13 = WindowsGetStringRawBuffer(string, 0);
    SponsoredUserName = v12(v11, v13);
    v6 = SponsoredUserName;
    if ( SponsoredUserName < 0 )
    {
      v10 = 6009;
      goto LABEL_7;
    }
    WindowsDeleteString(string);
    goto LABEL_11;
  }
  v10 = 6008;
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
0x1800977b0  mov     [rsp-18h+arg_8], rbx
0x1800977b5  push    rbp
0x1800977b6  push    rsi
0x1800977b7  push    rdi
0x1800977b8  mov     rbp, rsp
0x1800977bb  sub     rsp, 30h
0x1800977bf  mov     esi, edx
0x1800977c1  mov     rdi, rcx
0x1800977c4  lea     rbx, [rcx+228h]
0x1800977cb  mov     rax, [rbx]
0x1800977ce  mov     rcx, rbx
0x1800977d1  mov     rax, [rax+8]
0x1800977d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800977da  test    al, al
0x1800977dc  jz      loc_1800978E9
0x1800977e2  mov     [rbp+arg_10], 0
0x1800977ea  mov     [rbp+arg_18], 0
0x1800977f2  mov     qword ptr [rbp+var_10], 0
0x1800977fa  lea     rcx, [rbp+arg_18]
0x1800977fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097803  lea     r8, [rbp+arg_18]
0x180097807  lea     rdx, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5
0x18009780e  mov     rcx, rbx
0x180097811  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x180097816  mov     ebx, eax
0x180097818  test    eax, eax
0x18009781a  jns     short loc_180097826
0x18009781c  mov     edx, 1773h
0x180097821  jmp     loc_1800979ED
0x180097826  lea     eax, [rsi-1]
0x180097829  cmp     eax, 0Eh
0x18009782c  ja      loc_1800978F8
0x180097832  mov     [rbp+string], 0
0x18009783a  xor     ecx, ecx; string
0x18009783c  call    cs:__imp_WindowsDeleteString
0x180097842  mov     [rbp+string], 0
0x18009784a  lea     r8, [rbp+string]; HSTRING *
0x18009784e  mov     edx, esi; unsigned int
0x180097850  call    ?GetSponsoredUserName@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserManagerStatics::GetSponsoredUserName(uint,HSTRING__ * *)
0x180097855  mov     ebx, eax
0x180097857  test    eax, eax
0x180097859  jns     short loc_18009788B
0x18009785b  mov     edx, 1778h; void *
0x180097860  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180097867  mov     r9d, eax; char *
0x18009786a  mov     rcx, [rbp+18h]; this
0x18009786e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097873  nop
0x180097874  mov     rcx, [rbp+string]; string
0x180097878  call    cs:__imp_WindowsDeleteString
0x18009787e  mov     [rbp+string], 0
0x180097886  jmp     loc_180097A01
0x18009788b  mov     rdi, [rbp+arg_18]
0x18009788f  mov     rax, [rdi]
0x180097892  mov     rbx, [rax+250h]
0x180097899  xor     edx, edx; length
0x18009789b  mov     rcx, [rbp+string]; string
0x18009789f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800978a5  mov     rdx, rax
0x1800978a8  mov     rcx, rdi
0x1800978ab  mov     rax, rbx
0x1800978ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800978b3  mov     ebx, eax
0x1800978b5  test    eax, eax
0x1800978b7  jns     short loc_1800978C0
0x1800978b9  mov     edx, 1779h
0x1800978be  jmp     short loc_180097860
0x1800978c0  mov     rcx, [rbp+string]; string
0x1800978c4  call    cs:__imp_WindowsDeleteString
0x1800978ca  nop
0x1800978cb  lea     rcx, [rbp+var_10]
0x1800978cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800978d4  nop
0x1800978d5  lea     rcx, [rbp+arg_18]
0x1800978d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800978de  nop
0x1800978df  mov     rcx, [rbp+arg_10]; string
0x1800978e3  call    cs:__imp_WindowsDeleteString
0x1800978e9  xor     eax, eax
0x1800978eb  mov     rbx, [rsp+30h+arg_8]
0x1800978f0  add     rsp, 30h
0x1800978f4  pop     rdi
0x1800978f5  pop     rsi
0x1800978f6  pop     rbp
0x1800978f7  retn
0x1800978f8  mov     rdi, [rdi+218h]
0x1800978ff  mov     rax, [rdi]
0x180097902  mov     rbx, [rax+60h]
0x180097906  lea     rcx, [rbp+var_10]
0x18009790a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009790f  lea     r8, [rbp+var_10]
0x180097913  mov     edx, esi
0x180097915  mov     rcx, rdi
0x180097918  mov     rax, rbx
0x18009791b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097920  mov     ebx, eax
0x180097922  test    eax, eax
0x180097924  jns     short loc_180097930
0x180097926  mov     edx, 177Dh
0x18009792b  jmp     loc_1800979ED
0x180097930  mov     rdi, qword ptr [rbp+var_10]
0x180097934  mov     rax, [rdi]
0x180097937  mov     rbx, [rax+40h]
0x18009793b  mov     rcx, [rbp+arg_10]; string
0x18009793f  call    cs:__imp_WindowsDeleteString
0x180097945  mov     [rbp+arg_10], 0
0x18009794d  lea     rdx, [rbp+arg_10]
0x180097951  mov     rcx, rdi
0x180097954  mov     rax, rbx
0x180097957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009795c  mov     ebx, eax
0x18009795e  test    eax, eax
0x180097960  jns     short loc_18009796C
0x180097962  mov     edx, 177Eh
0x180097967  jmp     loc_1800979ED
0x18009796c  xor     edx, edx; length
0x18009796e  mov     rcx, [rbp+arg_10]; string
0x180097972  call    cs:__imp_WindowsGetStringRawBuffer
0x180097978  lea     rdx, asc_1801118C4; "@"
0x18009797f  mov     rcx, rax; Str
0x180097982  call    cs:__imp_wcsstr
0x180097988  test    rax, rax
0x18009798b  jz      loc_1800978CB
0x180097991  xor     edx, edx; length
0x180097993  mov     rcx, [rbp+arg_10]; string
0x180097997  call    cs:__imp_WindowsGetStringRawBuffer
0x18009799d  lea     rdx, SubStr; "\\"
0x1800979a4  mov     rcx, rax; Str
0x1800979a7  call    cs:__imp_wcsstr
0x1800979ad  test    rax, rax
0x1800979b0  jnz     loc_1800978CB
0x1800979b6  mov     rdi, [rbp+arg_18]
0x1800979ba  mov     rax, [rdi]
0x1800979bd  mov     rbx, [rax+250h]
0x1800979c4  xor     edx, edx; length
0x1800979c6  mov     rcx, [rbp+arg_10]; string
0x1800979ca  call    cs:__imp_WindowsGetStringRawBuffer
0x1800979d0  mov     rdx, rax
0x1800979d3  mov     rcx, rdi
0x1800979d6  mov     rax, rbx
0x1800979d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800979de  mov     ebx, eax
0x1800979e0  test    eax, eax
0x1800979e2  jns     loc_1800978CB
0x1800979e8  mov     edx, 1783h; void *
0x1800979ed  mov     r9d, eax; char *
0x1800979f0  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800979f7  mov     rcx, [rbp+18h]; this
0x1800979fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097a00  nop
0x180097a01  lea     rcx, [rbp+var_10]
0x180097a05  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097a0a  nop
0x180097a0b  lea     rcx, [rbp+arg_18]
0x180097a0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180097a14  nop
0x180097a15  mov     rcx, [rbp+arg_10]; string
0x180097a19  call    cs:__imp_WindowsDeleteString
0x180097a1f  mov     eax, ebx
0x180097a21  jmp     loc_1800978EB
```
