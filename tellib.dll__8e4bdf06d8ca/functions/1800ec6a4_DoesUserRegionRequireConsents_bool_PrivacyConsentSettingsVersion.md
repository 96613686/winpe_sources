# DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)

- ea: `0x1800ec6a4`
- end: `0x1800ec8e4`
- name: `?DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(bool *, enum PrivacyConsentSettingsVersion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801ee694`

## callees

- `0x180026ecc`
- `0x1800ec6a4`
- `0x18012de40`
- `0x18012eae4`
- `0x1801aa560`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ec85f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ec85f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec7b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec7f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec87d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec7b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec7f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec87d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec83e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec83e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800ec6fe`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800ec6fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DoesUserRegionRequireConsents(bool *a1, enum PrivacyConsentSettingsVersion *a2)
{
  int v3; // ebx
  __int64 v4; // rcx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  __int64 v9; // rcx
  wchar_t **i; // rdi
  const WCHAR *v11; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v13; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 v15; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  __int64 v17; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Globalization.GeographicRegion",
    0x27u,
    0x26u);
  v15 = 0;
  v17 = 0;
  v3 = RoActivateInstance(v19, &v17);
  if ( v3 >= 0 )
  {
    if ( !memcmp_0(&GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v15 = v17;
    }
    else
    {
      v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v17)(
             v17,
             &GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903,
             &v15);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\privacyconsenthelpers.h",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
    v4 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return (unsigned int)v3;
  }
  string = 0;
  v6 = v15;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(v6, &string);
  v3 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\privacyconsenthelpers.h",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
    WindowsDeleteString(string);
    string = 0;
    v9 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return (unsigned int)v3;
  }
  for ( i = &`DoesUserRegionRequireConsents'::`2'::RegionPrivacyRequirements; i != &off_180360680; i += 2 )
  {
    v11 = *i;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, v11, -1, 1) == 2 )
    {
      *a1 = 1;
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_19;
    }
  }
  *a1 = 0;
  WindowsDeleteString(string);
  string = 0;
LABEL_19:
  v13 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ec6a4  mov     [rsp-18h+arg_8], rbx
0x1800ec6a9  mov     [rsp-18h+arg_10], rsi
0x1800ec6ae  push    rbp
0x1800ec6af  push    rdi
0x1800ec6b0  push    r14
0x1800ec6b2  mov     rbp, rsp
0x1800ec6b5  sub     rsp, 70h
0x1800ec6b9  mov     rax, cs:__security_cookie
0x1800ec6c0  xor     rax, rsp
0x1800ec6c3  mov     [rbp+var_8], rax
0x1800ec6c7  mov     rsi, rcx
0x1800ec6ca  xor     r14d, r14d
0x1800ec6cd  mov     [rbp+var_40], r14
0x1800ec6d1  mov     [rbp+var_10], r14
0x1800ec6d5  lea     r9d, [r14+26h]; unsigned int
0x1800ec6d9  lea     r8d, [r14+27h]; unsigned int
0x1800ec6dd  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QB_WB; "Windows.Globalization.GeographicRegion"
0x1800ec6e4  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800ec6e8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x1800ec6ed  nop
0x1800ec6ee  mov     [rbp+var_40], r14
0x1800ec6f2  mov     [rbp+var_30], r14
0x1800ec6f6  lea     rdx, [rbp+var_30]
0x1800ec6fa  mov     rcx, [rbp+var_10]
0x1800ec6fe  call    cs:__imp_RoActivateInstance
0x1800ec705  nop     dword ptr [rax+rax+00h]
0x1800ec70a  mov     ebx, eax
0x1800ec70c  test    eax, eax
0x1800ec70e  js      short loc_1800EC762
0x1800ec710  lea     r8d, [r14+10h]; Size
0x1800ec714  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800ec71b  lea     rcx, _GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903; Buf1
0x1800ec722  call    memcmp_0
0x1800ec727  test    eax, eax
0x1800ec729  jnz     short loc_1800EC735
0x1800ec72b  mov     rax, [rbp+var_30]
0x1800ec72f  mov     [rbp+var_40], rax
0x1800ec733  jmp     short loc_1800EC762
0x1800ec735  mov     rcx, [rbp+var_30]
0x1800ec739  mov     rax, [rcx]
0x1800ec73c  lea     r8, [rbp+var_40]
0x1800ec740  lea     rdx, _GUID_01e9a621_4a64_4ed9_954f_9edeb07bd903
0x1800ec747  mov     rax, [rax]
0x1800ec74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec74f  mov     ebx, eax
0x1800ec751  mov     rcx, [rbp+var_30]
0x1800ec755  mov     rax, [rcx]
0x1800ec758  mov     rax, [rax+10h]
0x1800ec75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec761  nop
0x1800ec762  test    ebx, ebx
0x1800ec764  jns     short loc_1800EC7A0
0x1800ec766  mov     rcx, [rbp+18h]; this
0x1800ec76a  mov     r9d, ebx; char *
0x1800ec76d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800ec774  mov     edx, 0CFh; void *
0x1800ec779  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec77e  nop
0x1800ec77f  mov     rcx, [rbp+var_40]
0x1800ec783  test    rcx, rcx
0x1800ec786  jz      short loc_1800EC799
0x1800ec788  mov     [rbp+var_40], r14
0x1800ec78c  mov     rax, [rcx]
0x1800ec78f  mov     rax, [rax+10h]
0x1800ec793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec798  nop
0x1800ec799  mov     eax, ebx
0x1800ec79b  jmp     loc_1800EC8C2
0x1800ec7a0  mov     [rbp+string], r14
0x1800ec7a4  mov     rdi, [rbp+var_40]
0x1800ec7a8  mov     rax, [rdi]
0x1800ec7ab  mov     rbx, [rax+40h]
0x1800ec7af  xor     ecx, ecx; string
0x1800ec7b1  call    cs:__imp_WindowsDeleteString
0x1800ec7b8  nop     dword ptr [rax+rax+00h]
0x1800ec7bd  mov     [rbp+string], r14
0x1800ec7c1  lea     rdx, [rbp+string]
0x1800ec7c5  mov     rcx, rdi
0x1800ec7c8  mov     rax, rbx
0x1800ec7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec7d0  mov     ebx, eax
0x1800ec7d2  test    eax, eax
0x1800ec7d4  jns     short loc_1800EC822
0x1800ec7d6  mov     rcx, [rbp+18h]; this
0x1800ec7da  mov     r9d, eax; char *
0x1800ec7dd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800ec7e4  mov     edx, 0D2h; void *
0x1800ec7e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec7ee  nop
0x1800ec7ef  mov     rcx, [rbp+string]; string
0x1800ec7f3  call    cs:__imp_WindowsDeleteString
0x1800ec7fa  nop     dword ptr [rax+rax+00h]
0x1800ec7ff  mov     [rbp+string], r14
0x1800ec803  mov     rcx, [rbp+var_40]
0x1800ec807  test    rcx, rcx
0x1800ec80a  jz      short loc_1800EC81D
0x1800ec80c  mov     [rbp+var_40], r14
0x1800ec810  mov     rax, [rcx]
0x1800ec813  mov     rax, [rax+10h]
0x1800ec817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec81c  nop
0x1800ec81d  jmp     loc_1800EC799
0x1800ec822  lea     rdi, ?RegionPrivacyRequirements@?1??DoesUserRegionRequireConsents@@YAJPEA_NPEAW4PrivacyConsentSettingsVersion@@@Z@4QBU_unnamed_type_RegionPrivacyRequirements_@?1??1@YAJ01@Z@B; `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::_unnamed_type_RegionPrivacyRequirements_ const near * const `DoesUserRegionRequireConsents(bool *,PrivacyConsentSettingsVersion *)'::`2'::RegionPrivacyRequirements
0x1800ec829  lea     rax, off_180360680; "ShowedToastAtLevel"
0x1800ec830  cmp     rdi, rax
0x1800ec833  jz      short loc_1800EC88F
0x1800ec835  mov     rbx, [rdi]
0x1800ec838  xor     edx, edx; length
0x1800ec83a  mov     rcx, [rbp+string]; string
0x1800ec83e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec845  nop     dword ptr [rax+rax+00h]
0x1800ec84a  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x1800ec852  or      r9d, 0FFFFFFFFh; cchCount2
0x1800ec856  mov     r8, rbx; lpString2
0x1800ec859  or      edx, r9d; cchCount1
0x1800ec85c  mov     rcx, rax; lpString1
0x1800ec85f  call    cs:__imp_CompareStringOrdinal
0x1800ec866  nop     dword ptr [rax+rax+00h]
0x1800ec86b  cmp     eax, 2
0x1800ec86e  jz      short loc_1800EC876
0x1800ec870  add     rdi, 10h
0x1800ec874  jmp     short loc_1800EC829
0x1800ec876  mov     byte ptr [rsi], 1
0x1800ec879  mov     rcx, [rbp+string]; string
0x1800ec87d  call    cs:__imp_WindowsDeleteString
0x1800ec884  nop     dword ptr [rax+rax+00h]
0x1800ec889  mov     [rbp+string], r14
0x1800ec88d  jmp     short loc_1800EC8A6
0x1800ec88f  mov     [rsi], r14b
0x1800ec892  mov     rcx, [rbp+string]; string
0x1800ec896  call    cs:__imp_WindowsDeleteString
0x1800ec89d  nop     dword ptr [rax+rax+00h]
0x1800ec8a2  mov     [rbp+string], r14
0x1800ec8a6  mov     rcx, [rbp+var_40]
0x1800ec8aa  test    rcx, rcx
0x1800ec8ad  jz      short loc_1800EC8C0
0x1800ec8af  mov     [rbp+var_40], r14
0x1800ec8b3  mov     rax, [rcx]
0x1800ec8b6  mov     rax, [rax+10h]
0x1800ec8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec8bf  nop
0x1800ec8c0  xor     eax, eax
0x1800ec8c2  mov     rcx, [rbp+var_8]
0x1800ec8c6  xor     rcx, rsp; StackCookie
0x1800ec8c9  call    __security_check_cookie
0x1800ec8ce  lea     r11, [rsp+70h+var_s0]
0x1800ec8d3  mov     rbx, [r11+28h]
0x1800ec8d7  mov     rsi, [r11+30h]
0x1800ec8db  mov     rsp, r11
0x1800ec8de  pop     r14
0x1800ec8e0  pop     rdi
0x1800ec8e1  pop     rbp
0x1800ec8e2  retn
```
