# TryToResolveSid(ATL::CComBSTR const &)

- ea: `0x18000fa5c`
- end: `0x18000fca6`
- name: `?TryToResolveSid@@YAPEAGAEBVCComBSTR@ATL@@@Z`
- size: `586`
- prototype: `unsigned __int16 *__fastcall(const struct ATL::CComBSTR *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fa20`

## callees

- `0x18000fa5c`
- `0x18001f854`
- `0x1800205c0`
- `0x1800244e4`
- `0x1800249e4`
- `0x1800250ac`
- `0x18002f0f0`
- `0x18003d1b8`
- `0x18003dd20`
- `0x18004e700`
- `0x180052640`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000fb0d`
- `msvcrt!_wcsnicmp` at `0x18000fb31`
- `msvcrt!_wcsnicmp` at `0x18000fb0d`
- `msvcrt!_wcsnicmp` at `0x18000fb31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc72`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fc20`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fc50`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fc20`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fc50`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000fa95`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000fa95`

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
0x18000fa5c  mov     [rsp-8+arg_8], rbx
0x18000fa61  mov     [rsp-8+arg_10], rsi
0x18000fa66  push    rbp
0x18000fa67  push    rdi
0x18000fa68  push    r14
0x18000fa6a  lea     rbp, [rsp-47h]
0x18000fa6f  sub     rsp, 0E0h
0x18000fa76  mov     rax, cs:__security_cookie
0x18000fa7d  xor     rax, rsp
0x18000fa80  mov     [rbp+57h+var_20], rax
0x18000fa84  xor     r14d, r14d
0x18000fa87  mov     ebx, r14d
0x18000fa8a  mov     [rbp+57h+Sid], r14
0x18000fa8e  lea     rdx, [rbp+57h+Sid]; Sid
0x18000fa92  mov     rcx, [rcx]; StringSid
0x18000fa95  call    cs:__imp_ConvertStringSidToSidW
0x18000fa9c  nop     dword ptr [rax+rax+00h]
0x18000faa1  test    eax, eax
0x18000faa3  jz      loc_18000FC69
0x18000faa9  mov     rdx, [rbp+57h+Sid]; struct _SID *
0x18000faad  lea     rcx, [rbp+57h+var_A0]; this
0x18000fab1  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x18000fab6  nop
0x18000fab7  mov     rsi, [rbp+57h+String1]
0x18000fabb  cmp     [rsi-10h], r14d
0x18000fabf  jnz     short loc_18000FACE
0x18000fac1  lea     rcx, [rbp+57h+var_A0]; this
0x18000fac5  call    ?GetAccountNameAndDomain@CSid@ATL@@AEBAXXZ; ATL::CSid::GetAccountNameAndDomain(void)
0x18000faca  mov     rsi, [rbp+57h+String1]
0x18000face  mov     rdi, [rbp+57h+var_48]
0x18000fad2  cmp     [rdi-10h], r14d
0x18000fad6  jnz     short loc_18000FAE5
0x18000fad8  lea     rcx, [rbp+57h+var_A0]; this
0x18000fadc  call    ?GetAccountNameAndDomain@CSid@ATL@@AEBAXXZ; ATL::CSid::GetAccountNameAndDomain(void)
0x18000fae1  mov     rdi, [rbp+57h+var_48]
0x18000fae5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000fae9  mov     rax, rbx
0x18000faec  inc     rax
0x18000faef  cmp     [rdi+rax*2], r14w
0x18000faf4  jnz     short loc_18000FAEC
0x18000faf6  test    rax, rax
0x18000faf9  jnz     loc_18000FC4D
0x18000faff  lea     r8d, [rax+0Ch]; MaxCount
0x18000fb03  lea     rdx, aNtAuthority; "NT Authority"
0x18000fb0a  mov     rcx, rsi; String1
0x18000fb0d  call    cs:__imp__wcsnicmp
0x18000fb14  nop     dword ptr [rax+rax+00h]
0x18000fb19  test    eax, eax
0x18000fb1b  jz      loc_18000FC4D
0x18000fb21  mov     r8d, 7; MaxCount
0x18000fb27  lea     rdx, aBuiltin; "BUILTIN"
0x18000fb2e  mov     rcx, rsi; String1
0x18000fb31  call    cs:__imp__wcsnicmp
0x18000fb38  nop     dword ptr [rax+rax+00h]
0x18000fb3d  test    eax, eax
0x18000fb3f  jz      loc_18000FC4D
0x18000fb45  mov     rax, rbx
0x18000fb48  inc     rax
0x18000fb4b  cmp     [rsi+rax*2], r14w
0x18000fb50  jnz     short loc_18000FB48
0x18000fb52  test    rax, rax
0x18000fb55  jz      loc_18000FC3F
0x18000fb5b  mov     rax, rbx
0x18000fb5e  inc     rax
0x18000fb61  cmp     [rdi+rax*2], r14w
0x18000fb66  jnz     short loc_18000FB5E
0x18000fb68  test    rax, rax
0x18000fb6b  jz      loc_18000FC3F
0x18000fb71  mov     [rbp+57h+var_B0], 7
0x18000fb79  mov     [rbp+57h+var_B8], r14
0x18000fb7d  mov     word ptr [rbp+57h+psz], r14w
0x18000fb82  mov     rdx, rsi; Src
0x18000fb85  lea     rcx, [rbp+57h+psz]; void *
0x18000fb89  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fb8e  nop
0x18000fb8f  mov     rax, rbx
0x18000fb92  mov     rsi, [rbp+57h+var_B8]
0x18000fb96  sub     rax, rsi
0x18000fb99  cmp     rax, 1
0x18000fb9d  ja      short loc_18000FBAC
0x18000fb9f  lea     rcx, aStringTooLong; "string too long"
0x18000fba6  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000fbac  inc     rsi
0x18000fbaf  mov     rdx, rsi
0x18000fbb2  lea     rcx, [rbp+57h+psz]
0x18000fbb6  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x18000fbbb  test    al, al
0x18000fbbd  jz      short loc_18000FBEE
0x18000fbbf  mov     rcx, [rbp+57h+var_B8]
0x18000fbc3  lea     rax, [rbp+57h+psz]
0x18000fbc7  cmp     [rbp+57h+var_B0], 8
0x18000fbcc  cmovnb  rax, [rbp+57h+psz]
0x18000fbd1  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18000fbd7  lea     rcx, [rbp+57h+psz]
0x18000fbdb  cmp     [rbp+57h+var_B0], 8
0x18000fbe0  cmovnb  rcx, [rbp+57h+psz]
0x18000fbe5  mov     [rbp+57h+var_B8], rsi
0x18000fbe9  mov     [rcx+rsi*2], r14w
0x18000fbee  cmp     [rdi], r14w
0x18000fbf2  jnz     short loc_18000FBF9
0x18000fbf4  mov     rbx, r14
0x18000fbf7  jmp     short loc_18000FC03
0x18000fbf9  inc     rbx
0x18000fbfc  cmp     [rdi+rbx*2], r14w
0x18000fc01  jnz     short loc_18000FBF9
0x18000fc03  mov     r8, rbx
0x18000fc06  mov     rdx, rdi
0x18000fc09  lea     rcx, [rbp+57h+psz]
0x18000fc0d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18000fc12  lea     rcx, [rbp+57h+psz]
0x18000fc16  cmp     [rbp+57h+var_B0], 8
0x18000fc1b  cmovnb  rcx, [rbp+57h+psz]; psz
0x18000fc20  call    cs:__imp_SysAllocString
0x18000fc27  nop     dword ptr [rax+rax+00h]
0x18000fc2c  mov     rbx, rax
0x18000fc2f  xor     r8d, r8d
0x18000fc32  mov     dl, 1
0x18000fc34  lea     rcx, [rbp+57h+psz]
0x18000fc38  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000fc3d  jmp     short loc_18000FC5F
0x18000fc3f  lea     rcx, [rbp+57h+var_A0]; this
0x18000fc43  call    ?Sid@CSid@ATL@@QEBAPEBGXZ; ATL::CSid::Sid(void)
0x18000fc48  mov     rcx, rax
0x18000fc4b  jmp     short loc_18000FC50
0x18000fc4d  mov     rcx, rdi; psz
0x18000fc50  call    cs:__imp_SysAllocString
0x18000fc57  nop     dword ptr [rax+rax+00h]
0x18000fc5c  mov     rbx, rax
0x18000fc5f  lea     rcx, [rbp+57h+var_A0]; this
0x18000fc63  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18000fc68  nop
0x18000fc69  mov     rcx, [rbp+57h+Sid]; hMem
0x18000fc6d  test    rcx, rcx
0x18000fc70  jz      short loc_18000FC7E
0x18000fc72  call    cs:__imp_LocalFree
0x18000fc79  nop     dword ptr [rax+rax+00h]
0x18000fc7e  mov     rax, rbx
0x18000fc81  mov     rcx, [rbp+57h+var_20]
0x18000fc85  xor     rcx, rsp; StackCookie
0x18000fc88  call    __security_check_cookie
0x18000fc8d  lea     r11, [rsp+0F0h+var_10]
0x18000fc95  mov     rbx, [r11+28h]
0x18000fc99  mov     rsi, [r11+30h]
0x18000fc9d  mov     rsp, r11
0x18000fca0  pop     r14
0x18000fca2  pop     rdi
0x18000fca3  pop     rbp
0x18000fca4  retn
```
