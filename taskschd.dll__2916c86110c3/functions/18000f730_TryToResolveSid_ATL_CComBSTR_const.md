# TryToResolveSid(ATL::CComBSTR const &)

- ea: `0x18000f730`
- end: `0x18000f955`
- name: `?TryToResolveSid@@YAPEAGAEBVCComBSTR@ATL@@@Z`
- size: `549`
- prototype: `unsigned __int16 *__fastcall(const struct ATL::CComBSTR *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f6f4`

## callees

- `0x18000f730`
- `0x18001e81c`
- `0x18001f540`
- `0x1800228a0`
- `0x180022d44`
- `0x180023390`
- `0x18002cd60`
- `0x18003a684`
- `0x18003a9b0`
- `0x18004ab30`
- `0x18004e950`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000f7db`
- `msvcrt!_wcsnicmp` at `0x18000f7f9`
- `msvcrt!_wcsnicmp` at `0x18000f7db`
- `msvcrt!_wcsnicmp` at `0x18000f7f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f928`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f8e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f90c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f8e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f90c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000f769`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000f769`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
BSTR __fastcall TryToResolveSid(LPCWSTR *a1)
{
  BSTR v1; // rbx
  const unsigned __int16 *v2; // r8
  wchar_t *v3; // rsi
  OLECHAR *v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rsi
  OLECHAR **v10; // rax
  OLECHAR **v11; // rcx
  const OLECHAR *v12; // rcx
  __int64 v13; // rdx
  const OLECHAR *v14; // rcx
  PSID Sid; // [rsp+20h] [rbp-79h] BYREF
  OLECHAR *psz[2]; // [rsp+28h] [rbp-71h] BYREF
  __int64 v18; // [rsp+38h] [rbp-61h]
  unsigned __int64 v19; // [rsp+40h] [rbp-59h]
  _BYTE v20[88]; // [rsp+50h] [rbp-49h] BYREF
  OLECHAR *v21; // [rsp+A8h] [rbp+Fh]
  wchar_t *String1; // [rsp+B0h] [rbp+17h]

  v1 = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(*a1, &Sid) )
  {
    ATL::CSid::CSid((ATL::CSid *)v20, (const struct _SID *)Sid, v2);
    v3 = String1;
    if ( !*((_DWORD *)String1 - 4) )
    {
      ATL::CSid::GetAccountNameAndDomain((ATL::CSid *)v20);
      v3 = String1;
    }
    v4 = v21;
    if ( !*((_DWORD *)v21 - 4) )
    {
      ATL::CSid::GetAccountNameAndDomain((ATL::CSid *)v20);
      v4 = v21;
    }
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( v4[v6] );
    if ( !v6 && _wcsnicmp(v3, L"NT Authority", 0xCu) && _wcsnicmp(v3, L"BUILTIN", 7u) )
    {
      v7 = -1;
      do
        ++v7;
      while ( v3[v7] );
      if ( v7 )
      {
        v8 = -1;
        do
          ++v8;
        while ( v4[v8] );
        if ( v8 )
        {
          v19 = 7;
          v18 = 0;
          LOWORD(psz[0]) = 0;
          std::wstring::assign(psz, v3);
          if ( (unsigned __int64)(-1 - v18) <= 1 )
            std::_Xlength_error("string too long");
          v9 = v18 + 1;
          if ( (unsigned __int8)std::wstring::_Grow(psz, v18 + 1) )
          {
            v10 = psz;
            if ( v19 >= 8 )
              v10 = (OLECHAR **)psz[0];
            *((_WORD *)v10 + v18) = 92;
            v11 = psz;
            if ( v19 >= 8 )
              v11 = (OLECHAR **)psz[0];
            v18 = v9;
            *((_WORD *)v11 + v9) = 0;
          }
          if ( *v4 )
          {
            do
              ++v5;
            while ( v4[v5] );
          }
          else
          {
            v5 = 0;
          }
          std::wstring::append(psz, v4, v5);
          v12 = (const OLECHAR *)psz;
          if ( v19 >= 8 )
            v12 = psz[0];
          v1 = SysAllocString(v12);
          LOBYTE(v13) = 1;
          std::wstring::_Tidy(psz, v13, 0);
          goto LABEL_34;
        }
      }
      v14 = ATL::CSid::Sid((ATL::CSid *)v20);
    }
    else
    {
      v14 = v4;
    }
    v1 = SysAllocString(v14);
LABEL_34:
    ATL::CSid::~CSid((ATL::CSid *)v20);
  }
  if ( Sid )
    LocalFree(Sid);
  return v1;
}

```

## disassembly

```asm
0x18000f730  mov     [rsp-8+arg_8], rbx
0x18000f735  mov     [rsp-8+arg_10], rsi
0x18000f73a  push    rbp
0x18000f73b  push    rdi
0x18000f73c  push    r14
0x18000f73e  lea     rbp, [rsp-47h]
0x18000f743  sub     rsp, 0E0h
0x18000f74a  mov     rax, cs:__security_cookie
0x18000f751  xor     rax, rsp
0x18000f754  mov     [rbp+57h+var_20], rax
0x18000f758  xor     r14d, r14d
0x18000f75b  mov     ebx, r14d
0x18000f75e  mov     [rbp+57h+Sid], r14
0x18000f762  lea     rdx, [rbp+57h+Sid]; Sid
0x18000f766  mov     rcx, [rcx]; StringSid
0x18000f769  call    cs:__imp_ConvertStringSidToSidW
0x18000f76f  test    eax, eax
0x18000f771  jz      loc_18000F91F
0x18000f777  mov     rdx, [rbp+57h+Sid]; struct _SID *
0x18000f77b  lea     rcx, [rbp+57h+var_A0]; this
0x18000f77f  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x18000f784  nop
0x18000f785  mov     rsi, [rbp+57h+String1]
0x18000f789  cmp     [rsi-10h], r14d
0x18000f78d  jnz     short loc_18000F79C
0x18000f78f  lea     rcx, [rbp+57h+var_A0]; this
0x18000f793  call    ?GetAccountNameAndDomain@CSid@ATL@@AEBAXXZ; ATL::CSid::GetAccountNameAndDomain(void)
0x18000f798  mov     rsi, [rbp+57h+String1]
0x18000f79c  mov     rdi, [rbp+57h+var_48]
0x18000f7a0  cmp     [rdi-10h], r14d
0x18000f7a4  jnz     short loc_18000F7B3
0x18000f7a6  lea     rcx, [rbp+57h+var_A0]; this
0x18000f7aa  call    ?GetAccountNameAndDomain@CSid@ATL@@AEBAXXZ; ATL::CSid::GetAccountNameAndDomain(void)
0x18000f7af  mov     rdi, [rbp+57h+var_48]
0x18000f7b3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f7b7  mov     rax, rbx
0x18000f7ba  inc     rax
0x18000f7bd  cmp     [rdi+rax*2], r14w
0x18000f7c2  jnz     short loc_18000F7BA
0x18000f7c4  test    rax, rax
0x18000f7c7  jnz     loc_18000F909
0x18000f7cd  lea     r8d, [rax+0Ch]; MaxCount
0x18000f7d1  lea     rdx, aNtAuthority; "NT Authority"
0x18000f7d8  mov     rcx, rsi; String1
0x18000f7db  call    cs:__imp__wcsnicmp
0x18000f7e1  test    eax, eax
0x18000f7e3  jz      loc_18000F909
0x18000f7e9  mov     r8d, 7; MaxCount
0x18000f7ef  lea     rdx, aBuiltin; "BUILTIN"
0x18000f7f6  mov     rcx, rsi; String1
0x18000f7f9  call    cs:__imp__wcsnicmp
0x18000f7ff  test    eax, eax
0x18000f801  jz      loc_18000F909
0x18000f807  mov     rax, rbx
0x18000f80a  inc     rax
0x18000f80d  cmp     [rsi+rax*2], r14w
0x18000f812  jnz     short loc_18000F80A
0x18000f814  test    rax, rax
0x18000f817  jz      loc_18000F8FB
0x18000f81d  mov     rax, rbx
0x18000f820  inc     rax
0x18000f823  cmp     [rdi+rax*2], r14w
0x18000f828  jnz     short loc_18000F820
0x18000f82a  test    rax, rax
0x18000f82d  jz      loc_18000F8FB
0x18000f833  mov     [rbp+57h+var_B0], 7
0x18000f83b  mov     [rbp+57h+var_B8], r14
0x18000f83f  mov     word ptr [rbp+57h+psz], r14w
0x18000f844  mov     rdx, rsi; Src
0x18000f847  lea     rcx, [rbp+57h+psz]; void *
0x18000f84b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000f850  nop
0x18000f851  mov     rax, rbx
0x18000f854  mov     rsi, [rbp+57h+var_B8]
0x18000f858  sub     rax, rsi
0x18000f85b  cmp     rax, 1
0x18000f85f  ja      short loc_18000F86E
0x18000f861  lea     rcx, aStringTooLong; "string too long"
0x18000f868  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f86e  inc     rsi
0x18000f871  mov     rdx, rsi
0x18000f874  lea     rcx, [rbp+57h+psz]
0x18000f878  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x18000f87d  test    al, al
0x18000f87f  jz      short loc_18000F8B0
0x18000f881  mov     rcx, [rbp+57h+var_B8]
0x18000f885  lea     rax, [rbp+57h+psz]
0x18000f889  cmp     [rbp+57h+var_B0], 8
0x18000f88e  cmovnb  rax, [rbp+57h+psz]
0x18000f893  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18000f899  lea     rcx, [rbp+57h+psz]
0x18000f89d  cmp     [rbp+57h+var_B0], 8
0x18000f8a2  cmovnb  rcx, [rbp+57h+psz]
0x18000f8a7  mov     [rbp+57h+var_B8], rsi
0x18000f8ab  mov     [rcx+rsi*2], r14w
0x18000f8b0  cmp     [rdi], r14w
0x18000f8b4  jnz     short loc_18000F8BB
0x18000f8b6  mov     rbx, r14
0x18000f8b9  jmp     short loc_18000F8C5
0x18000f8bb  inc     rbx
0x18000f8be  cmp     [rdi+rbx*2], r14w
0x18000f8c3  jnz     short loc_18000F8BB
0x18000f8c5  mov     r8, rbx
0x18000f8c8  mov     rdx, rdi
0x18000f8cb  lea     rcx, [rbp+57h+psz]
0x18000f8cf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000f8d4  lea     rcx, [rbp+57h+psz]
0x18000f8d8  cmp     [rbp+57h+var_B0], 8
0x18000f8dd  cmovnb  rcx, [rbp+57h+psz]; psz
0x18000f8e2  call    cs:__imp_SysAllocString
0x18000f8e8  mov     rbx, rax
0x18000f8eb  xor     r8d, r8d
0x18000f8ee  mov     dl, 1
0x18000f8f0  lea     rcx, [rbp+57h+psz]
0x18000f8f4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f8f9  jmp     short loc_18000F915
0x18000f8fb  lea     rcx, [rbp+57h+var_A0]; this
0x18000f8ff  call    ?Sid@CSid@ATL@@QEBAPEBGXZ; ATL::CSid::Sid(void)
0x18000f904  mov     rcx, rax
0x18000f907  jmp     short loc_18000F90C
0x18000f909  mov     rcx, rdi; psz
0x18000f90c  call    cs:__imp_SysAllocString
0x18000f912  mov     rbx, rax
0x18000f915  lea     rcx, [rbp+57h+var_A0]; this
0x18000f919  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18000f91e  nop
0x18000f91f  mov     rcx, [rbp+57h+Sid]; hMem
0x18000f923  test    rcx, rcx
0x18000f926  jz      short loc_18000F92E
0x18000f928  call    cs:__imp_LocalFree
0x18000f92e  mov     rax, rbx
0x18000f931  mov     rcx, [rbp+57h+var_20]
0x18000f935  xor     rcx, rsp; StackCookie
0x18000f938  call    __security_check_cookie
0x18000f93d  lea     r11, [rsp+0F0h+var_10]
0x18000f945  mov     rbx, [r11+28h]
0x18000f949  mov     rsi, [r11+30h]
0x18000f94d  mov     rsp, r11
0x18000f950  pop     r14
0x18000f952  pop     rdi
0x18000f953  pop     rbp
0x18000f954  retn
```
