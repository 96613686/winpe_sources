# GetPackageType(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x180026480`
- end: `0x18002675a`
- name: `?GetPackageType@@YA?AW4PackageType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `730`
- prototype: `__int64 __fastcall(std::filesystem::path *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006df80`

## callees

- `0x180025064`
- `0x180025348`
- `0x180025364`
- `0x18002540c`
- `0x18002589c`
- `0x180026480`
- `0x180026860`
- `0x180027af0`
- `0x18015cb00`
- `0x18027758c`
- `0x1802775f4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002652c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800265b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002660d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026648`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800266d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002652c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800265b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002660d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026648`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800266d5`

## string_xrefs

- `0x180026556`: `shellcommon\undockeddevkit\libs\windowsudk.applicationmodel.appextensions\PackageIdentityHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetPackageType(std::filesystem::path *this)
{
  std::filesystem::path *v2; // rdx
  __int64 RetailPackageFamilyName; // rax
  unsigned int v4; // edi
  const WCHAR *v5; // r14
  const WCHAR *v6; // r15
  __int64 BuiltInPackageFamilyName; // rax
  char v8; // bl
  bool v9; // al
  const WCHAR *v10; // rcx
  const WCHAR *v11; // r8
  winrt::hstring *v12; // rax
  const WCHAR *v13; // rax
  const WCHAR *v14; // rcx
  int v15; // ebx
  const WCHAR *v17; // rcx
  const char *v18; // [rsp+28h] [rbp-71h]
  _BYTE v19[8]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v20[8]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v21[8]; // [rsp+48h] [rbp-51h] BYREF
  std::filesystem::path *v22; // [rsp+50h] [rbp-49h]
  LPCWCH lpString2[3]; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int64 v24; // [rsp+78h] [rbp-21h]
  LPCWCH lpString1[3]; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int64 v26; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v22 = this;
  if ( *((_QWORD *)this + 3) <= 7u )
    v2 = this;
  else
    v2 = *(std::filesystem::path **)this;
  PackageFamilyNameAndPublisherIdFromPackageFullName(lpString2, v2);
  RetailPackageFamilyName = GetRetailPackageFamilyName(v19);
  v4 = 1;
  v5 = &String1;
  if ( *(_QWORD *)RetailPackageFamilyName )
    v6 = *(const WCHAR **)(*(_QWORD *)RetailPackageFamilyName + 16LL);
  else
    v6 = &String1;
  BuiltInPackageFamilyName = GetBuiltInPackageFamilyName(v21);
  v8 = 3;
  if ( *(_QWORD *)BuiltInPackageFamilyName )
    v5 = *(const WCHAR **)(*(_QWORD *)BuiltInPackageFamilyName + 16LL);
  v9 = 0;
  if ( CompareStringOrdinal(v5, -1, v6, -1, 1) == 2 )
  {
    v8 = 7;
    if ( *(_QWORD *)GetBuiltInPackageFamilyName(v20) )
      v9 = 1;
  }
  wil::details::in1diag3::FailFast_IfMsg(
    retaddr,
    (void *)0x6A,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.applicationmodel.appextensions\\PackageIdentityHelpers.h",
    (const char *)v9,
    (bool)"Incorrect registration of Shell Undocked Package PFNs - both BuiltIn and Retail package cannot have the same name",
    v18);
  if ( (v8 & 4) != 0 )
  {
    v8 &= ~4u;
    winrt::handle_type<winrt::impl::hstring_traits>::close(v20);
  }
  if ( (v8 & 2) != 0 )
  {
    v8 &= ~2u;
    winrt::handle_type<winrt::impl::hstring_traits>::close(v21);
  }
  if ( (v8 & 1) != 0 )
    winrt::handle_type<winrt::impl::hstring_traits>::close(v19);
  v10 = (const WCHAR *)lpString1;
  if ( v26 > 7 )
    v10 = lpString1[0];
  if ( CompareStringOrdinal(v10, -1, L"cw5n1h2txyewy", -1, 1) == 2 )
  {
    if ( __TSS0__4__GetPackageType__YA_AW4PackageType__V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
    {
      Init_thread_header(&__TSS0__4__GetPackageType__YA_AW4PackageType__V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___Z_4HA);
      if ( __TSS0__4__GetPackageType__YA_AW4PackageType__V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___Z_4HA == -1 )
      {
        `GetPackageType'::`5'::maxLen = 17;
        Init_thread_footer(&__TSS0__4__GetPackageType__YA_AW4PackageType__V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___Z_4HA);
      }
    }
    v11 = (const WCHAR *)lpString2;
    if ( v24 > 7 )
      v11 = lpString2[0];
    if ( CompareStringOrdinal(
           L"MicrosoftWindows.",
           `GetPackageType'::`5'::maxLen,
           v11,
           `GetPackageType'::`5'::maxLen,
           1) == 2 )
    {
      v12 = (winrt::hstring *)GetBuiltInPackageFamilyName(v19);
      v13 = winrt::hstring::c_str(v12);
      v14 = (const WCHAR *)lpString2;
      if ( v24 > 7 )
        v14 = lpString2[0];
      v15 = CompareStringOrdinal(v14, -1, v13, -1, 1);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v19);
      if ( v15 != 2 )
        v4 = 4;
    }
    else
    {
      v4 = 2;
    }
  }
  else
  {
    v17 = (const WCHAR *)lpString1;
    if ( v26 > 7 )
      v17 = lpString1[0];
    v4 = 5;
    if ( CompareStringOrdinal(v17, -1, L"8wekyb3d8bbwe", -1, 1) == 2 )
      v4 = 3;
  }
  std::filesystem::path::~path((std::filesystem::path *)lpString1);
  std::filesystem::path::~path((std::filesystem::path *)lpString2);
  std::filesystem::path::~path(this);
  return v4;
}

```

## disassembly

```asm
0x180026480  push    rbp
0x180026482  push    rbx
0x180026483  push    rsi
0x180026484  push    rdi
0x180026485  push    r12
0x180026487  push    r13
0x180026489  push    r14
0x18002648b  push    r15
0x18002648d  lea     rbp, [rsp-1Fh]
0x180026492  sub     rsp, 0B8h
0x180026499  mov     rax, cs:__security_cookie
0x1800264a0  xor     rax, rsp
0x1800264a3  mov     [rbp+57h+var_50], rax
0x1800264a7  mov     rsi, rcx
0x1800264aa  mov     [rbp+57h+var_A0], rcx
0x1800264ae  mov     [rbp+57h+var_C0], 0
0x1800264b5  cmp     qword ptr [rcx+18h], 7
0x1800264ba  jbe     loc_1800266AE
0x1800264c0  mov     rdx, [rcx]
0x1800264c3  lea     rcx, [rbp+57h+lpString2]
0x1800264c7  call    ?PackageFamilyNameAndPublisherIdFromPackageFullName@@YA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEB_W@Z; PackageFamilyNameAndPublisherIdFromPackageFullName(wchar_t const *)
0x1800264cc  nop
0x1800264cd  lea     rcx, [rbp+57h+var_B8]
0x1800264d1  call    ?GetRetailPackageFamilyName@@YA?AUhstring@winrt@@XZ; GetRetailPackageFamilyName(void)
0x1800264d6  nop
0x1800264d7  mov     edi, 1
0x1800264dc  mov     [rbp+57h+var_C0], edi
0x1800264df  mov     rcx, [rax]
0x1800264e2  lea     r14, String1
0x1800264e9  test    rcx, rcx
0x1800264ec  jz      loc_18002669D
0x1800264f2  mov     r15, [rcx+10h]
0x1800264f6  lea     rcx, [rbp+57h+var_A8]
0x1800264fa  call    ?GetBuiltInPackageFamilyName@@YA?AUhstring@winrt@@XZ; GetBuiltInPackageFamilyName(void)
0x1800264ff  nop
0x180026500  mov     r13d, 3
0x180026506  mov     ebx, r13d
0x180026509  mov     [rbp+57h+var_C0], ebx
0x18002650c  mov     rcx, [rax]
0x18002650f  test    rcx, rcx
0x180026512  jnz     loc_1800266A5
0x180026518  mov     [rsp+0F0h+bIgnoreCase], edi; bIgnoreCase
0x18002651c  or      r12d, 0FFFFFFFFh
0x180026520  mov     r9d, r12d; cchCount2
0x180026523  mov     r8, r15; lpString2
0x180026526  mov     edx, r12d; cchCount1
0x180026529  mov     rcx, r14; lpString1
0x18002652c  call    cs:__imp_CompareStringOrdinal
0x180026532  lea     r14d, [r12+3]
0x180026537  cmp     eax, r14d
0x18002653a  jz      loc_1800266F4
0x180026540  xor     eax, eax
0x180026542  mov     rcx, [rbp+5Fh]; this
0x180026546  lea     rdx, aIncorrectRegis; "Incorrect registration of Shell Undocke"...
0x18002654d  mov     qword ptr [rsp+0F0h+bIgnoreCase], rdx; bool
0x180026552  movzx   r9d, al; char *
0x180026556  lea     r8, aShellcommonUnd_79; "shellcommon\\undockeddevkit\\libs\\wind"...
0x18002655d  mov     edx, 6Ah ; 'j'; void *
0x180026562  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x180026567  mov     r15d, 4
0x18002656d  test    r15b, bl
0x180026570  jnz     loc_180026714
0x180026576  test    r14b, bl
0x180026579  jz      short loc_180026588
0x18002657b  and     ebx, 0FFFFFFFDh
0x18002657e  lea     rcx, [rbp+57h+var_A8]
0x180026582  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180026587  nop
0x180026588  test    dil, bl
0x18002658b  jz      short loc_180026596
0x18002658d  lea     rcx, [rbp+57h+var_B8]
0x180026591  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180026596  lea     rcx, [rbp+57h+lpString1]
0x18002659a  cmp     [rbp+57h+var_58], 7
0x18002659f  cmova   rcx, [rbp+57h+lpString1]; lpString1
0x1800265a4  mov     [rsp+0F0h+bIgnoreCase], edi; bIgnoreCase
0x1800265a8  mov     r9d, r12d; cchCount2
0x1800265ab  lea     r8, String2; "cw5n1h2txyewy"
0x1800265b2  mov     edx, r12d; cchCount1
0x1800265b5  call    cs:__imp_CompareStringOrdinal
0x1800265bb  cmp     eax, r14d
0x1800265be  jnz     loc_1800266B6
0x1800265c4  mov     ecx, cs:_tls_index
0x1800265ca  mov     rax, gs:58h
0x1800265d3  mov     edx, 4
0x1800265d8  mov     rax, [rax+rcx*8]
0x1800265dc  mov     ecx, [rdx+rax]
0x1800265df  cmp     cs:?$TSS0@?4??GetPackageType@@YA?AW4PackageType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@4HA, ecx
0x1800265e5  jg      loc_180026725
0x1800265eb  mov     edx, cs:?maxLen@?4??GetPackageType@@YA?AW4PackageType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@4HB; cchCount1
0x1800265f1  lea     r8, [rbp+57h+lpString2]
0x1800265f5  cmp     [rbp+57h+var_78], 7
0x1800265fa  cmova   r8, [rbp+57h+lpString2]; lpString2
0x1800265ff  mov     [rsp+0F0h+bIgnoreCase], edi; bIgnoreCase
0x180026603  mov     r9d, edx; cchCount2
0x180026606  lea     rcx, aMicrosoftwindo_12; "MicrosoftWindows."
0x18002660d  call    cs:__imp_CompareStringOrdinal
0x180026613  cmp     eax, r14d
0x180026616  jnz     loc_1800266EC
0x18002661c  lea     rcx, [rbp+57h+var_B8]
0x180026620  call    ?GetBuiltInPackageFamilyName@@YA?AUhstring@winrt@@XZ; GetBuiltInPackageFamilyName(void)
0x180026625  mov     rcx, rax; this
0x180026628  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18002662d  lea     rcx, [rbp+57h+lpString2]
0x180026631  cmp     [rbp+57h+var_78], 7
0x180026636  cmova   rcx, [rbp+57h+lpString2]; lpString1
0x18002663b  mov     [rsp+0F0h+bIgnoreCase], edi; bIgnoreCase
0x18002663f  mov     r9d, r12d; cchCount2
0x180026642  mov     r8, rax; lpString2
0x180026645  mov     edx, r12d; cchCount1
0x180026648  call    cs:__imp_CompareStringOrdinal
0x18002664e  mov     ebx, eax
0x180026650  lea     rcx, [rbp+57h+var_B8]
0x180026654  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180026659  cmp     ebx, r14d
0x18002665c  cmovnz  edi, r15d
0x180026660  lea     rcx, [rbp+57h+lpString1]; this
0x180026664  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180026669  lea     rcx, [rbp+57h+lpString2]; this
0x18002666d  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180026672  nop
0x180026673  mov     rcx, rsi; this
0x180026676  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x18002667b  mov     eax, edi
0x18002667d  mov     rcx, [rbp+57h+var_50]
0x180026681  xor     rcx, rsp; StackCookie
0x180026684  call    __security_check_cookie
0x180026689  add     rsp, 0B8h
0x180026690  pop     r15
0x180026692  pop     r14
0x180026694  pop     r13
0x180026696  pop     r12
0x180026698  pop     rdi
0x180026699  pop     rsi
0x18002669a  pop     rbx
0x18002669b  pop     rbp
0x18002669c  retn
0x18002669d  mov     r15, r14
0x1800266a0  jmp     loc_1800264F6
0x1800266a5  mov     r14, [rcx+10h]
0x1800266a9  jmp     loc_180026518
0x1800266ae  mov     rdx, rsi
0x1800266b1  jmp     loc_1800264C3
0x1800266b6  lea     rcx, [rbp+57h+lpString1]
0x1800266ba  cmp     [rbp+57h+var_58], 7
0x1800266bf  cmova   rcx, [rbp+57h+lpString1]; lpString1
0x1800266c4  mov     [rsp+0F0h+bIgnoreCase], edi; bIgnoreCase
0x1800266c8  mov     r9d, r12d; cchCount2
0x1800266cb  lea     r8, a8wekyb3d8bbwe; "8wekyb3d8bbwe"
0x1800266d2  mov     edx, r12d; cchCount1
0x1800266d5  call    cs:__imp_CompareStringOrdinal
0x1800266db  mov     edi, 5
0x1800266e0  cmp     eax, r14d
0x1800266e3  cmovz   edi, r13d
0x1800266e7  jmp     loc_180026660
0x1800266ec  mov     edi, r14d
0x1800266ef  jmp     loc_180026660
0x1800266f4  lea     rcx, [rbp+57h+var_B0]
0x1800266f8  call    ?GetBuiltInPackageFamilyName@@YA?AUhstring@winrt@@XZ; GetBuiltInPackageFamilyName(void)
0x1800266fd  mov     ebx, 7
0x180026702  cmp     qword ptr [rax], 0
0x180026706  jz      loc_180026540
0x18002670c  mov     al, dil
0x18002670f  jmp     loc_180026542
0x180026714  and     ebx, 0FFFFFFFBh
0x180026717  lea     rcx, [rbp+57h+var_B0]
0x18002671b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180026720  jmp     loc_180026576
0x180026725  lea     rcx, ?$TSS0@?4??GetPackageType@@YA?AW4PackageType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@4HA
0x18002672c  call    _Init_thread_header
0x180026731  cmp     cs:?$TSS0@?4??GetPackageType@@YA?AW4PackageType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@4HA, r12d
0x180026738  jnz     loc_1800265EB
0x18002673e  mov     cs:?maxLen@?4??GetPackageType@@YA?AW4PackageType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@4HB, 11h; int const `GetPackageType(std::wstring)'::`5'::maxLen
0x180026748  lea     rcx, ?$TSS0@?4??GetPackageType@@YA?AW4PackageType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@4HA
0x18002674f  call    _Init_thread_footer
0x180026754  jmp     loc_1800265EB
```
