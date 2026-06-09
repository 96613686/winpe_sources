# EMIECacheContainerString

- ea: `0x180014500`
- end: `0x18001472a`
- name: `EMIECacheContainerString`
- size: `554`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800143cc`
- `0x180014500`
- `0x180096aec`
- `0x1800b9d24`

## callees

- `0x180014500`
- `0x1800162d4`
- `0x1800a25dc`
- `0x1800af5b0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800146c4`
- `msvcrt!wcscat_s` at `0x1800146e1`
- `msvcrt!wcscat_s` at `0x1800146c4`
- `msvcrt!wcscat_s` at `0x1800146e1`
- `msvcrt!wcscpy_s` at `0x1800146a3`
- `msvcrt!wcscpy_s` at `0x1800146a3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180014517`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180014618`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180014517`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180014618`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x180014545`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18001468c`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x180014545`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18001468c`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180014530`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180014530`

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
            v2 = &word_18016B450;
            if ( !word_18016B450 )
            {
              v7 = EMIECacheContainerString(L"EmieSiteListDualEngine");
              v8 = StringCchPrintfW(&word_18016B450, 0x58u, L"%s:", v7);
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
    v2 = (wchar_t *)qword_18016B3A0;
    goto LABEL_22;
  }
  if ( a1 == L"EmieSiteList:" )
  {
    v2 = &word_18016B450;
    goto LABEL_22;
  }
  if ( a1 == L"EmieUserList:" )
  {
    v2 = (wchar_t *)qword_18016B500;
    goto LABEL_22;
  }
  return a1;
}

```

## disassembly

```asm
0x180014500  mov     [rsp+arg_0], rbx
0x180014505  mov     [rsp+arg_8], rbp
0x18001450a  push    rdi
0x18001450b  sub     rsp, 30h
0x18001450f  mov     rdi, rcx
0x180014512  mov     ecx, 1000003Fh
0x180014517  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18001451e  nop     dword ptr [rax+rax+00h]
0x180014523  xor     ebp, ebp
0x180014525  test    al, al
0x180014527  jnz     loc_180014613
0x18001452d  mov     rbx, rdi
0x180014530  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180014537  nop     dword ptr [rax+rax+00h]
0x18001453c  test    al, al
0x18001453e  jz      short loc_18001458B
0x180014540  mov     ecx, 10000054h
0x180014545  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18001454c  nop     dword ptr [rax+rax+00h]
0x180014551  test    rax, rax
0x180014554  jz      short loc_18001458B
0x180014556  cmp     [rax], bp
0x180014559  jz      short loc_18001458B
0x18001455b  lea     rcx, aEmiesitelistdu; "EmieSiteListDualEngine"
0x180014562  cmp     rdi, rcx
0x180014565  jz      loc_1800146FA
0x18001456b  lea     rax, aEmiesitelistdu_0; "EmieSiteListDualEngine:"
0x180014572  cmp     rdi, rax
0x180014575  jnz     loc_180014713
0x18001457b  cmp     cs:word_18016B450, bp
0x180014582  lea     rbx, word_18016B450
0x180014589  jz      short loc_1800145D9
0x18001458b  mov     rax, rbx
0x18001458e  mov     rbx, [rsp+38h+arg_0]
0x180014593  mov     rbp, [rsp+38h+arg_8]
0x180014598  add     rsp, 30h
0x18001459c  pop     rdi
0x18001459d  retn
0x18001459f  mov     r9, rcx
0x1800145a2  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800145a7  mov     rcx, rbx; unsigned __int16 *
0x1800145aa  lea     r8, aSS_3; "%s%s"
0x1800145b1  mov     edx, 58h ; 'X'; unsigned __int64
0x1800145b6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800145bb  test    eax, eax
0x1800145bd  jns     short loc_18001458B
0x1800145bf  mov     rcx, [rsp+38h]; this
0x1800145c4  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\urlmon\\browsermo"...
0x1800145cb  mov     r9d, eax; char *
0x1800145ce  mov     edx, 87h; void *
0x1800145d3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800145d9  call    EMIECacheContainerString
0x1800145de  mov     r9, rax
0x1800145e1  lea     r8, aS; "%s:"
0x1800145e8  mov     edx, 58h ; 'X'; unsigned __int64
0x1800145ed  mov     rcx, rbx; unsigned __int16 *
0x1800145f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800145f5  test    eax, eax
0x1800145f7  jns     short loc_18001458B
0x1800145f9  mov     rcx, [rsp+38h]; this
0x1800145fe  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\urlmon\\browsermo"...
0x180014605  mov     r9d, eax; char *
0x180014608  mov     edx, 90h; void *
0x18001460d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180014613  mov     ecx, 10000037h
0x180014618  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18001461f  nop     dword ptr [rax+rax+00h]
0x180014624  test    al, al
0x180014626  jnz     loc_18001452D
0x18001462c  lea     rax, aEmiesitelist_0; "EmieSiteList"
0x180014633  cmp     rdi, rax
0x180014636  jnz     short loc_180014641
0x180014638  lea     rbx, Destination
0x18001463f  jmp     short loc_18001467E
0x180014641  lea     rax, aEmieuserlist_0; "EmieUserList"
0x180014648  cmp     rdi, rax
0x18001464b  jnz     short loc_180014656
0x18001464d  lea     rbx, qword_18016B3A0
0x180014654  jmp     short loc_18001467E
0x180014656  lea     rax, aEmiesitelist; "EmieSiteList:"
0x18001465d  cmp     rdi, rax
0x180014660  jnz     short loc_18001466B
0x180014662  lea     rbx, word_18016B450
0x180014669  jmp     short loc_18001467E
0x18001466b  lea     rax, aEmieuserlist; "EmieUserList:"
0x180014672  cmp     rdi, rax
0x180014675  jnz     short loc_1800146F2
0x180014677  lea     rbx, qword_18016B500
0x18001467e  cmp     [rbx], bp
0x180014681  jnz     loc_18001458B
0x180014687  mov     ecx, 1000002Bh
0x18001468c  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x180014693  nop     dword ptr [rax+rax+00h]
0x180014698  mov     edx, 58h ; 'X'; SizeInWords
0x18001469d  mov     rcx, rbx; Destination
0x1800146a0  mov     r8, rax; Source
0x1800146a3  call    cs:__imp_wcscpy_s
0x1800146aa  nop     dword ptr [rax+rax+00h]
0x1800146af  test    eax, eax
0x1800146b1  jnz     loc_18001458B
0x1800146b7  lea     r8, asc_180140160; "_"
0x1800146be  mov     rcx, rbx; Destination
0x1800146c1  lea     edx, [rax+58h]; SizeInWords
0x1800146c4  call    cs:__imp_wcscat_s
0x1800146cb  nop     dword ptr [rax+rax+00h]
0x1800146d0  test    eax, eax
0x1800146d2  jnz     loc_18001458B
0x1800146d8  mov     r8, rdi; Source
0x1800146db  lea     edx, [rax+58h]; SizeInWords
0x1800146de  mov     rcx, rbx; Destination
0x1800146e1  call    cs:__imp_wcscat_s
0x1800146e8  nop     dword ptr [rax+rax+00h]
0x1800146ed  jmp     loc_18001458B
0x1800146f2  mov     rax, rdi
0x1800146f5  jmp     loc_18001458E
0x1800146fa  cmp     cs:Destination, bp
0x180014701  lea     rbx, Destination
0x180014708  jnz     loc_18001458B
0x18001470e  jmp     loc_18001459F
0x180014713  mov     rcx, [rsp+38h]; this
0x180014718  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\urlmon\\browsermo"...
0x18001471f  mov     edx, 96h; void *
0x180014724  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
