# Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool,void *)

- ea: `0x180048ff4`
- end: `0x180049377`
- name: `?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z`
- size: `899`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `100`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027e64`
- `0x180047e58`
- `0x180053dfc`
- `0x18006d4d4`
- `0x18006de80`
- `0x18006e038`
- `0x18006e7e4`
- `0x18006f9f0`
- `0x1800701fc`
- `0x1800705e4`
- `0x18007a918`
- `0x18007fdb0`
- `0x1800805d8`
- `0x1800828f4`
- `0x180082b70`
- `0x180082ce8`
- `0x180085230`
- `0x180085700`
- `0x180085d00`
- `0x180086440`
- `0x18008674c`
- `0x1800872f0`
- `0x180088da8`
- `0x18008bd3c`
- `0x18008db34`
- `0x180099fb4`
- `0x18009be24`
- `0x1800a265c`
- `0x1800a87dc`
- `0x1800a9c80`
- `0x1800ab10c`
- `0x1800ab394`
- `0x1800b0910`
- `0x1800cfb90`
- `0x1800eb718`
- `0x1800f2748`
- `0x1800f5ad0`
- `0x1800f71d4`
- `0x1800f748c`
- `0x1800f9de8`
- `0x18010176c`
- `0x18010621c`
- `0x180108668`
- `0x18010e330`
- `0x18011d0bc`
- `0x18011e840`
- `0x180122d68`
- `0x180126740`
- `0x1801702d8`
- `0x180178a30`

## callees

- `0x18001d160`
- `0x180031fb8`
- `0x180032718`
- `0x180034d94`
- `0x180048ff4`
- `0x180049380`
- `0x1800495cc`
- `0x1800498f0`
- `0x18004be40`
- `0x180080054`
- `0x180089d90`
- `0x1800a1e24`
- `0x1800d0d9c`
- `0x18012de40`
- `0x180161064`
- `0x180161298`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049289`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800490c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800490c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800490de`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800490de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004920c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004920c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800492b4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180049308`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800492b4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180049308`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x180049190`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x180049190`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004909c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004909c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(
        _QWORD *lpSrc,
        char a2,
        void *a3)
{
  int v5; // eax
  BOOL v6; // eax
  const char *v7; // r9
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  HANDLE CurrentThread; // rax
  unsigned int i; // edi
  WCHAR *v12; // r8
  const WCHAR *v13; // rdx
  const wchar_t *v14; // rcx
  int result; // eax
  WCHAR *v16; // rdx
  const WCHAR *v17; // rcx
  const char *v18; // r9
  DWORD v19; // eax
  const char *v20; // r9
  WCHAR *v21; // rdx
  const WCHAR *v22; // rcx
  const char *v23; // r9
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-60h]
  void *TokenHandle[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v26[2]; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR lpDest[2]; // [rsp+50h] [rbp-30h] BYREF
  DWORD dwSize[2]; // [rsp+60h] [rbp-20h]
  unsigned __int64 v29; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( a2 )
  {
    *(_OWORD *)v26 = *(_OWORD *)&off_1803478E0;
    *(_OWORD *)lpDest = *(_OWORD *)&off_1803478F0;
    v5 = Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(lpSrc);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x343,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
        (const char *)(unsigned int)v5,
        TokenType);
  }
  TokenHandle[0] = 0;
  if ( a3 )
  {
    TokenHandle[0] = 0;
    v6 = DuplicateTokenEx(a3, 0xEu, 0, SecurityIdentification, TokenImpersonation, TokenHandle);
    v8 = retaddr;
    if ( v6 )
      goto LABEL_11;
    v9 = 848;
    goto LABEL_10;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, TokenHandle) && GetLastError() != 1008 )
  {
    v9 = 857;
    v8 = retaddr;
LABEL_10:
    wil::details::in1diag3::_Log_GetLastError(
      v8,
      (void *)v9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
      v7);
  }
LABEL_11:
  if ( (unsigned __int64)TokenHandle[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( GetLastError() != 1008 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x384,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
        v18);
  }
  else
  {
    *(_OWORD *)lpDest = 0;
    *(_QWORD *)dwSize = 0;
    v29 = 0;
    std::wstring::_Construct<0,wchar_t>(lpDest, 0, 260);
    for ( i = 260; ; std::wstring::resize(lpDest, i) )
    {
      v12 = (WCHAR *)lpDest;
      if ( v29 > 7 )
        v12 = lpDest[0];
      v13 = lpSrc[3] <= 7u ? (const WCHAR *)lpSrc : (const WCHAR *)*lpSrc;
      if ( ExpandEnvironmentStringsForUserW(TokenHandle[0], v13, v12, dwSize[0]) )
        break;
      if ( i >= 0x410 )
      {
        std::wstring::_Assign<wchar_t>((char **)lpSrc, &Src, 0);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpDest);
        result = LODWORD(TokenHandle[0]) - 1;
        if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          return CloseHandle(TokenHandle[0]);
        return result;
      }
      i *= 2;
    }
    v26[0] = 0;
    v14 = (const wchar_t *)lpDest;
    if ( v29 > 7 )
      v14 = lpDest[0];
    if ( (int)StringCchLengthW(v14, i, v26) < 0 )
    {
      std::wstring::_Assign<wchar_t>((char **)lpSrc, &Src, 0);
      goto LABEL_47;
    }
    std::wstring::resize(lpDest, LODWORD(v26[0]));
    std::wstring::operator=(lpSrc, lpDest);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpDest);
  }
  if ( std::wstring::find_first_of(lpSrc, 37, 0) != -1 )
  {
    std::wstring::wstring(lpDest, 260, 0);
    v16 = (WCHAR *)lpDest;
    if ( v29 > 7 )
      v16 = lpDest[0];
    if ( lpSrc[3] <= 7u )
      v17 = (const WCHAR *)lpSrc;
    else
      v17 = (const WCHAR *)*lpSrc;
    v19 = ExpandEnvironmentStringsW(v17, v16, dwSize[0]);
    if ( !v19 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x390,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
        v20);
    if ( (unsigned __int64)v19 >= *(_QWORD *)dwSize )
    {
      std::wstring::resize(lpDest, v19);
      v21 = (WCHAR *)lpDest;
      if ( v29 > 7 )
        v21 = lpDest[0];
      if ( lpSrc[3] <= 7u )
        v22 = (const WCHAR *)lpSrc;
      else
        v22 = (const WCHAR *)*lpSrc;
      v19 = ExpandEnvironmentStringsW(v22, v21, dwSize[0]);
      if ( !v19 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x397,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
          v23);
    }
    std::wstring::resize(lpDest, v19 - 1);
    std::wstring::operator=(lpSrc, lpDest);
LABEL_47:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpDest);
  }
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
}

```

## disassembly

```asm
0x180048ff4  mov     [rsp-18h+arg_8], rbx
0x180048ff9  push    rbp
0x180048ffa  push    rdi
0x180048ffb  push    r14
0x180048ffd  mov     rbp, rsp
0x180049000  sub     rsp, 80h
0x180049007  mov     rax, cs:__security_cookie
0x18004900e  xor     rax, rsp
0x180049011  mov     [rbp+var_10], rax
0x180049015  mov     rdi, r8
0x180049018  mov     rbx, rcx
0x18004901b  lea     r14, aOnecoreBaseTel_73; "onecore\\base\\telemetry\\utc\\include"...
0x180049022  test    dl, dl
0x180049024  jz      short loc_180049066
0x180049026  movups  xmm1, xmmword ptr cs:off_1803478E0; "%DiagtrackStorageRoot%"
0x18004902d  movups  xmm0, xmmword ptr cs:off_1803478F0; "%ProgramData%\\Microsoft\\Diagnosis"
0x180049034  movdqa  xmmword ptr [rbp+var_40], xmm1
0x180049039  movdqa  xmmword ptr [rbp+lpDest], xmm0
0x18004903e  xor     r9d, r9d
0x180049041  lea     r8, [rbp+var_40]
0x180049045  lea     rdx, [rbp+lpDest]
0x180049049  call    ??$ReplaceAllImpl@_W@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1_N@Z; Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(std::wstring &,std::wstring_view,std::wstring_view,bool)
0x18004904e  mov     rcx, [rbp+18h]; this
0x180049052  test    eax, eax
0x180049054  jns     short loc_180049066
0x180049056  mov     r9d, eax; char *
0x180049059  mov     r8, r14; unsigned int
0x18004905c  mov     edx, 343h; void *
0x180049061  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049066  mov     [rbp+TokenHandle], 0
0x18004906e  test    rdi, rdi
0x180049071  jz      short loc_1800490B7
0x180049073  mov     [rbp+TokenHandle], 0
0x18004907b  lea     rax, [rbp+TokenHandle]
0x18004907f  mov     [rsp+80h+phNewToken], rax; phNewToken
0x180049084  mov     [rsp+80h+TokenType], 2; TokenType
0x18004908c  mov     r9d, 1; ImpersonationLevel
0x180049092  xor     r8d, r8d; lpTokenAttributes
0x180049095  lea     edx, [r9+0Dh]; dwDesiredAccess
0x180049099  mov     rcx, rdi; hExistingToken
0x18004909c  call    cs:__imp_DuplicateTokenEx
0x1800490a3  nop     dword ptr [rax+rax+00h]
0x1800490a8  mov     rcx, [rbp+18h]
0x1800490ac  test    eax, eax
0x1800490ae  jnz     short loc_180049115
0x1800490b0  mov     edx, 350h
0x1800490b5  jmp     short loc_18004910D
0x1800490b7  xor     edx, edx
0x1800490b9  lea     rcx, [rbp+TokenHandle]
0x1800490bd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800490c2  call    cs:__imp_GetCurrentThread
0x1800490c9  nop     dword ptr [rax+rax+00h]
0x1800490ce  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800490d2  mov     edx, 0Eh; DesiredAccess
0x1800490d7  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800490db  mov     rcx, rax; ThreadHandle
0x1800490de  call    cs:__imp_OpenThreadToken
0x1800490e5  nop     dword ptr [rax+rax+00h]
0x1800490ea  test    eax, eax
0x1800490ec  jnz     short loc_180049115
0x1800490ee  mov     rdi, [rbp+18h]
0x1800490f2  call    cs:__imp_GetLastError
0x1800490f9  nop     dword ptr [rax+rax+00h]
0x1800490fe  cmp     eax, 3F0h
0x180049103  jz      short loc_180049115
0x180049105  mov     edx, 359h; void *
0x18004910a  mov     rcx, rdi; this
0x18004910d  mov     r8, r14; unsigned int
0x180049110  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180049115  mov     rax, [rbp+TokenHandle]
0x180049119  dec     rax
0x18004911c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180049120  ja      loc_180049285
0x180049126  xorps   xmm0, xmm0
0x180049129  movups  xmmword ptr [rbp+lpDest], xmm0
0x18004912d  mov     qword ptr [rbp+dwSize], 0
0x180049135  mov     [rbp+var_18], 0
0x18004913d  xor     edx, edx
0x18004913f  mov     r8d, 104h
0x180049145  lea     rcx, [rbp+lpDest]
0x180049149  call    ??$_Construct@$0A@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAX_W_K@Z; std::wstring::_Construct<0,wchar_t>(wchar_t,unsigned __int64)
0x18004914e  nop
0x18004914f  mov     edi, 104h
0x180049154  jmp     short loc_18004916B
0x180049156  cmp     edi, 410h
0x18004915c  jnb     short loc_1800491DD
0x18004915e  add     edi, edi
0x180049160  mov     edx, edi
0x180049162  lea     rcx, [rbp+lpDest]
0x180049166  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18004916b  lea     r8, [rbp+lpDest]
0x18004916f  cmp     [rbp+var_18], 7
0x180049174  cmova   r8, [rbp+lpDest]; lpDest
0x180049179  cmp     qword ptr [rbx+18h], 7
0x18004917e  jbe     short loc_180049185
0x180049180  mov     rdx, [rbx]
0x180049183  jmp     short loc_180049188
0x180049185  mov     rdx, rbx; lpSrc
0x180049188  mov     r9d, [rbp+dwSize]; dwSize
0x18004918c  mov     rcx, [rbp+TokenHandle]; hToken
0x180049190  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x180049197  nop     dword ptr [rax+rax+00h]
0x18004919c  test    eax, eax
0x18004919e  jz      short loc_180049156
0x1800491a0  mov     [rbp+var_40], 0
0x1800491a8  lea     rcx, [rbp+lpDest]
0x1800491ac  cmp     [rbp+var_18], 7
0x1800491b1  cmova   rcx, [rbp+lpDest]; wchar_t *
0x1800491b6  mov     edx, edi; unsigned __int64
0x1800491b8  lea     r8, [rbp+var_40]; unsigned __int64 *
0x1800491bc  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1800491c1  test    eax, eax
0x1800491c3  jns     short loc_18004921D
0x1800491c5  xor     r8d, r8d
0x1800491c8  lea     rdx, Src
0x1800491cf  mov     rcx, rbx
0x1800491d2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800491d7  nop
0x1800491d8  jmp     loc_180049343
0x1800491dd  xor     r8d, r8d
0x1800491e0  lea     rdx, Src
0x1800491e7  mov     rcx, rbx
0x1800491ea  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800491ef  nop
0x1800491f0  lea     rcx, [rbp+lpDest]; this
0x1800491f4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800491f9  nop
0x1800491fa  mov     rcx, [rbp+TokenHandle]; hObject
0x1800491fe  lea     rax, [rcx-1]
0x180049202  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180049206  ja      loc_180049356
0x18004920c  call    cs:__imp_CloseHandle
0x180049213  nop     dword ptr [rax+rax+00h]
0x180049218  jmp     loc_180049356
0x18004921d  mov     edx, dword ptr [rbp+var_40]
0x180049220  lea     rcx, [rbp+lpDest]
0x180049224  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180049229  lea     rdx, [rbp+lpDest]
0x18004922d  mov     rcx, rbx
0x180049230  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180049235  nop
0x180049236  lea     rcx, [rbp+lpDest]; this
0x18004923a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18004923f  mov     edx, 25h ; '%'
0x180049244  xor     r8d, r8d
0x180049247  mov     rcx, rbx
0x18004924a  call    ?find_first_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_first_of(wchar_t,unsigned __int64)
0x18004924f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049253  jz      loc_18004934D
0x180049259  xor     r8d, r8d
0x18004925c  mov     edx, 104h
0x180049261  lea     rcx, [rbp+lpDest]
0x180049265  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18004926a  nop
0x18004926b  lea     rdx, [rbp+lpDest]
0x18004926f  cmp     [rbp+var_18], 7
0x180049274  cmova   rdx, [rbp+lpDest]; lpDst
0x180049279  cmp     qword ptr [rbx+18h], 7
0x18004927e  jbe     short loc_1800492AD
0x180049280  mov     rcx, [rbx]
0x180049283  jmp     short loc_1800492B0
0x180049285  mov     rdi, [rbp+18h]
0x180049289  call    cs:__imp_GetLastError
0x180049290  nop     dword ptr [rax+rax+00h]
0x180049295  cmp     eax, 3F0h
0x18004929a  jz      short loc_18004923F
0x18004929c  mov     r8, r14; unsigned int
0x18004929f  mov     edx, 384h; void *
0x1800492a4  mov     rcx, rdi; this
0x1800492a7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800492ad  mov     rcx, rbx; lpSrc
0x1800492b0  mov     r8d, [rbp+dwSize]; nSize
0x1800492b4  call    cs:__imp_ExpandEnvironmentStringsW
0x1800492bb  nop     dword ptr [rax+rax+00h]
0x1800492c0  mov     rcx, [rbp+18h]; this
0x1800492c4  test    eax, eax
0x1800492c6  jnz     short loc_1800492D6
0x1800492c8  mov     r8, r14; unsigned int
0x1800492cb  mov     edx, 390h; void *
0x1800492d0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800492d6  mov     edx, eax
0x1800492d8  cmp     rdx, qword ptr [rbp+dwSize]
0x1800492dc  jb      short loc_18004932A
0x1800492de  lea     rcx, [rbp+lpDest]
0x1800492e2  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800492e7  lea     rdx, [rbp+lpDest]
0x1800492eb  cmp     [rbp+var_18], 7
0x1800492f0  cmova   rdx, [rbp+lpDest]; lpDst
0x1800492f5  cmp     qword ptr [rbx+18h], 7
0x1800492fa  jbe     short loc_180049301
0x1800492fc  mov     rcx, [rbx]
0x1800492ff  jmp     short loc_180049304
0x180049301  mov     rcx, rbx; lpSrc
0x180049304  mov     r8d, [rbp+dwSize]; nSize
0x180049308  call    cs:__imp_ExpandEnvironmentStringsW
0x18004930f  nop     dword ptr [rax+rax+00h]
0x180049314  mov     rcx, [rbp+18h]; this
0x180049318  test    eax, eax
0x18004931a  jnz     short loc_18004932A
0x18004931c  mov     r8, r14; unsigned int
0x18004931f  mov     edx, 397h; void *
0x180049324  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004932a  lea     edx, [rax-1]
0x18004932d  lea     rcx, [rbp+lpDest]
0x180049331  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180049336  lea     rdx, [rbp+lpDest]
0x18004933a  mov     rcx, rbx
0x18004933d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180049342  nop
0x180049343  lea     rcx, [rbp+lpDest]; this
0x180049347  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18004934c  nop
0x18004934d  lea     rcx, [rbp+TokenHandle]
0x180049351  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180049356  mov     rcx, [rbp+var_10]
0x18004935a  xor     rcx, rsp; StackCookie
0x18004935d  call    __security_check_cookie
0x180049362  mov     rbx, [rsp+80h+arg_8]
0x18004936a  add     rsp, 80h
0x180049371  pop     r14
0x180049373  pop     rdi
0x180049374  pop     rbp
0x180049375  retn
```
