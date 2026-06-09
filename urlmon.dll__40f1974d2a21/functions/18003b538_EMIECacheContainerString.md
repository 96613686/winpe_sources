# EMIECacheContainerString

- ea: `0x18003b538`
- end: `0x18003b731`
- name: `EMIECacheContainerString`
- size: `505`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b40c`
- `0x18003b538`
- `0x180090694`
- `0x1800b24f4`

## callees

- `0x18001054c`
- `0x18003b538`
- `0x18009b9dc`
- `0x1800a856c`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18003b6d7`
- `msvcrt!wcscat_s` at `0x18003b6ee`
- `msvcrt!wcscat_s` at `0x18003b6d7`
- `msvcrt!wcscat_s` at `0x18003b6ee`
- `msvcrt!wcscpy_s` at `0x18003b6bc`
- `msvcrt!wcscpy_s` at `0x18003b6bc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003b54f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003b63d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003b54f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18003b63d`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18003b571`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18003b6ab`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18003b571`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18003b6ab`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003b562`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003b562`

## pseudocode

```c
wchar_t *__fastcall EMIECacheContainerString(wchar_t *a1)
{
  wchar_t *v2; // rbx
  _WORD *String; // rax
  const char *v4; // r9
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  const wchar_t *v9; // rax
  int v10; // [rsp+20h] [rbp-18h]
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !(unsigned __int8)IEConfiguration_GetBool(268435519) || (unsigned __int8)IEConfiguration_GetBool(268435511) )
  {
    v2 = a1;
    if ( IsDualEngineProcess() )
    {
      String = (_WORD *)IEConfiguration_GetString(268435540);
      if ( String )
      {
        if ( *String )
        {
          if ( a1 == L"EmieSiteListDualEngine" )
          {
            v2 = &Destination;
            if ( !Destination )
            {
              v11 = (int)String;
              v6 = StringCchPrintfW(&Destination, 0x58u, L"%s%s", L"EmieSiteListDualEngine");
              if ( v6 < 0 )
                wil::details::in1diag3::_FailFast_Hr(
                  retaddr,
                  (void *)0x87,
                  (unsigned int)"onecoreuap\\inetcore\\urlmon\\browsermode\\ieenterprisemodefilter.cpp",
                  (const char *)(unsigned int)v6,
                  v11);
            }
          }
          else
          {
            if ( a1 != L"EmieSiteListDualEngine:" )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x96,
                (unsigned int)"onecoreuap\\inetcore\\urlmon\\browsermode\\ieenterprisemodefilter.cpp",
                v4);
            v2 = &word_18015E350;
            if ( !word_18015E350 )
            {
              v7 = EMIECacheContainerString(L"EmieSiteListDualEngine");
              v8 = StringCchPrintfW(&word_18015E350, 0x58u, L"%s:", v7);
              if ( v8 < 0 )
                wil::details::in1diag3::_FailFast_Hr(
                  retaddr,
                  (void *)0x90,
                  (unsigned int)"onecoreuap\\inetcore\\urlmon\\browsermode\\ieenterprisemodefilter.cpp",
                  (const char *)(unsigned int)v8,
                  v10);
            }
          }
        }
      }
    }
    return v2;
  }
  if ( a1 == L"EmieSiteList" )
  {
    v2 = &Destination;
LABEL_22:
    if ( !*v2 )
    {
      v9 = (const wchar_t *)IEConfiguration_GetString(268435499);
      if ( !wcscpy_s(v2, 0x58u, v9) && !wcscat_s(v2, 0x58u, L"_") )
        wcscat_s(v2, 0x58u, a1);
    }
    return v2;
  }
  if ( a1 == L"EmieUserList" )
  {
    v2 = (wchar_t *)qword_18015E2A0;
    goto LABEL_22;
  }
  if ( a1 == L"EmieSiteList:" )
  {
    v2 = &word_18015E350;
    goto LABEL_22;
  }
  if ( a1 == L"EmieUserList:" )
  {
    v2 = (wchar_t *)qword_18015E400;
    goto LABEL_22;
  }
  return a1;
}

```

## disassembly

```asm
0x18003b538  mov     [rsp+arg_0], rbx
0x18003b53d  mov     [rsp+arg_8], rbp
0x18003b542  push    rdi
0x18003b543  sub     rsp, 30h
0x18003b547  mov     rdi, rcx
0x18003b54a  mov     ecx, 1000003Fh
0x18003b54f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18003b555  xor     ebp, ebp
0x18003b557  test    al, al
0x18003b559  jnz     loc_18003B638
0x18003b55f  mov     rbx, rdi
0x18003b562  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18003b568  test    al, al
0x18003b56a  jz      short loc_18003B5B1
0x18003b56c  mov     ecx, 10000054h
0x18003b571  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18003b577  test    rax, rax
0x18003b57a  jz      short loc_18003B5B1
0x18003b57c  cmp     [rax], bp
0x18003b57f  jz      short loc_18003B5B1
0x18003b581  lea     rcx, aEmiesitelistdu; "EmieSiteListDualEngine"
0x18003b588  cmp     rdi, rcx
0x18003b58b  jz      loc_18003B701
0x18003b591  lea     rax, aEmiesitelistdu_0; "EmieSiteListDualEngine:"
0x18003b598  cmp     rdi, rax
0x18003b59b  jnz     loc_18003B71A
0x18003b5a1  cmp     cs:word_18015E350, bp
0x18003b5a8  lea     rbx, word_18015E350
0x18003b5af  jz      short loc_18003B5FE
0x18003b5b1  mov     rax, rbx
0x18003b5b4  mov     rbx, [rsp+38h+arg_0]
0x18003b5b9  mov     rbp, [rsp+38h+arg_8]
0x18003b5be  add     rsp, 30h
0x18003b5c2  pop     rdi
0x18003b5c3  retn
0x18003b5c4  mov     r9, rcx
0x18003b5c7  mov     qword ptr [rsp+38h+var_18], rax; int
0x18003b5cc  mov     rcx, rbx; unsigned __int16 *
0x18003b5cf  lea     r8, aSS_3; "%s%s"
0x18003b5d6  mov     edx, 58h ; 'X'; unsigned __int64
0x18003b5db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b5e0  test    eax, eax
0x18003b5e2  jns     short loc_18003B5B1
0x18003b5e4  mov     rcx, [rsp+38h]; this
0x18003b5e9  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\urlmon\\browsermo"...
0x18003b5f0  mov     r9d, eax; char *
0x18003b5f3  mov     edx, 87h; void *
0x18003b5f8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18003b5fe  call    EMIECacheContainerString
0x18003b603  mov     r9, rax
0x18003b606  lea     r8, aS; "%s:"
0x18003b60d  mov     edx, 58h ; 'X'; unsigned __int64
0x18003b612  mov     rcx, rbx; unsigned __int16 *
0x18003b615  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b61a  test    eax, eax
0x18003b61c  jns     short loc_18003B5B1
0x18003b61e  mov     rcx, [rsp+38h]; this
0x18003b623  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\urlmon\\browsermo"...
0x18003b62a  mov     r9d, eax; char *
0x18003b62d  mov     edx, 90h; void *
0x18003b632  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18003b638  mov     ecx, 10000037h
0x18003b63d  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18003b643  test    al, al
0x18003b645  jnz     loc_18003B55F
0x18003b64b  lea     rax, aEmiesitelist_0; "EmieSiteList"
0x18003b652  cmp     rdi, rax
0x18003b655  jnz     short loc_18003B660
0x18003b657  lea     rbx, Destination
0x18003b65e  jmp     short loc_18003B69D
0x18003b660  lea     rax, aEmieuserlist_0; "EmieUserList"
0x18003b667  cmp     rdi, rax
0x18003b66a  jnz     short loc_18003B675
0x18003b66c  lea     rbx, qword_18015E2A0
0x18003b673  jmp     short loc_18003B69D
0x18003b675  lea     rax, aEmiesitelist; "EmieSiteList:"
0x18003b67c  cmp     rdi, rax
0x18003b67f  jnz     short loc_18003B68A
0x18003b681  lea     rbx, word_18015E350
0x18003b688  jmp     short loc_18003B69D
0x18003b68a  lea     rax, aEmieuserlist; "EmieUserList:"
0x18003b691  cmp     rdi, rax
0x18003b694  jnz     short loc_18003B6F9
0x18003b696  lea     rbx, qword_18015E400
0x18003b69d  cmp     [rbx], bp
0x18003b6a0  jnz     loc_18003B5B1
0x18003b6a6  mov     ecx, 1000002Bh
0x18003b6ab  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18003b6b1  mov     edx, 58h ; 'X'; SizeInWords
0x18003b6b6  mov     rcx, rbx; Destination
0x18003b6b9  mov     r8, rax; Source
0x18003b6bc  call    cs:__imp_wcscpy_s
0x18003b6c2  test    eax, eax
0x18003b6c4  jnz     loc_18003B5B1
0x18003b6ca  lea     r8, asc_180133160; "_"
0x18003b6d1  mov     rcx, rbx; Destination
0x18003b6d4  lea     edx, [rax+58h]; SizeInWords
0x18003b6d7  call    cs:__imp_wcscat_s
0x18003b6dd  test    eax, eax
0x18003b6df  jnz     loc_18003B5B1
0x18003b6e5  mov     r8, rdi; Source
0x18003b6e8  lea     edx, [rax+58h]; SizeInWords
0x18003b6eb  mov     rcx, rbx; Destination
0x18003b6ee  call    cs:__imp_wcscat_s
0x18003b6f4  jmp     loc_18003B5B1
0x18003b6f9  mov     rax, rdi
0x18003b6fc  jmp     loc_18003B5B4
0x18003b701  cmp     cs:Destination, bp
0x18003b708  lea     rbx, Destination
0x18003b70f  jnz     loc_18003B5B1
0x18003b715  jmp     loc_18003B5C4
0x18003b71a  mov     rcx, [rsp+38h]; this
0x18003b71f  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\urlmon\\browsermo"...
0x18003b726  mov     edx, 96h; void *
0x18003b72b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
