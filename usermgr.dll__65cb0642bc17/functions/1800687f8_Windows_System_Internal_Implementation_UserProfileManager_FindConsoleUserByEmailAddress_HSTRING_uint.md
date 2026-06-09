# Windows::System::Internal::Implementation::UserProfileManager::FindConsoleUserByEmailAddress(HSTRING__ *,uint *)

- ea: `0x1800687f8`
- end: `0x180068a33`
- name: `?FindConsoleUserByEmailAddress@UserProfileManager@Implementation@Internal@System@Windows@@AEAAJPEAUHSTRING__@@PEAI@Z`
- size: `571`
- prototype: `int(Windows::System::Internal::Implementation::UserProfileManager *__hidden this, HSTRING, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180068770`
- `0x1800c21d0`

## callees

- `0x18000acdc`
- `0x180025cd4`
- `0x180037e98`
- `0x1800687f8`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800688f3`
- `msvcrt!_wcsicmp` at `0x180068956`
- `msvcrt!_wcsicmp` at `0x1800688f3`
- `msvcrt!_wcsicmp` at `0x180068956`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068875`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800688e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800688e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180068842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180068842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800688b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068916`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068968`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006897a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800689c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800689f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800688b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068916`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068968`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006897a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800689c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800689f9`

## string_xrefs

- `0x180068829`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180068852`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180068a0c`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`
- `0x180068a21`: `onecore\ds\security\umstartup\usermgr\lib\knownusermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::System::Internal::Implementation::UserProfileManager::FindConsoleUserByEmailAddress(
        Windows::System::Internal::Implementation::UserProfileManager *this,
        HSTRING a2,
        unsigned int *a3)
{
  const wchar_t *StringRawBuffer; // r12
  __int64 v7; // rbx
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rdi
  int v10; // eax
  const wchar_t *v11; // rax
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rdi
  int v14; // eax
  const wchar_t *v15; // rax
  __int64 v16; // rcx
  __int64 i; // rax
  char *v19; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  HSTRING v21; // [rsp+70h] [rbp+40h] BYREF
  HSTRING string; // [rsp+78h] [rbp+48h] BYREF

  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
      (const char *)0x80004003LL,
      (int)v19);
  if ( WindowsIsStringEmpty(a2) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
      (const char *)0x80070057LL,
      (int)v19);
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v19 = (char *)this + 64;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = **((_QWORD **)this + 13);
  while ( v7 != *((_QWORD *)this + 13) )
  {
    string = 0;
    v8 = *(_QWORD *)(v7 + 40);
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(v8, &string);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)(unsigned int)v10,
        (int)v19);
    v11 = WindowsGetStringRawBuffer(string, 0);
    if ( v11 && !_wcsicmp(StringRawBuffer, v11) )
    {
      *a3 = *(_DWORD *)(v7 + 32);
LABEL_22:
      WindowsDeleteString(string);
      break;
    }
    v21 = 0;
    v12 = *(_QWORD *)(v7 + 40);
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 64LL);
    WindowsDeleteString(0);
    v21 = 0;
    v14 = v13(v12, &v21);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\knownusermanager.cpp",
        (const char *)(unsigned int)v14,
        (int)v19);
    v15 = WindowsGetStringRawBuffer(v21, 0);
    if ( v15 && !_wcsicmp(StringRawBuffer, v15) )
    {
      *a3 = *(_DWORD *)(v7 + 32);
      WindowsDeleteString(v21);
      v21 = 0;
      goto LABEL_22;
    }
    WindowsDeleteString(v21);
    v21 = 0;
    WindowsDeleteString(string);
    if ( !*(_BYTE *)(v7 + 25) )
    {
      v16 = *(_QWORD *)(v7 + 16);
      if ( *(_BYTE *)(v16 + 25) )
      {
        for ( i = *(_QWORD *)(v7 + 8); !*(_BYTE *)(i + 25) && v7 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v7 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(v16);
      }
      v7 = i;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v19);
  return 0;
}

```

## disassembly

```asm
0x1800687f8  mov     [rsp-28h+arg_0], rbx
0x1800687fd  mov     [rsp-28h+arg_8], rsi
0x180068802  push    rbp
0x180068803  push    rdi
0x180068804  push    r12
0x180068806  push    r14
0x180068808  push    r15
0x18006880a  mov     rbp, rsp
0x18006880d  sub     rsp, 30h
0x180068811  mov     r14, r8
0x180068814  mov     rdi, rdx
0x180068817  mov     r15, rcx
0x18006881a  mov     rcx, [rbp+28h]; this
0x18006881e  test    r8, r8
0x180068821  jnz     short loc_18006883B
0x180068823  mov     r9d, 80004003h; char *
0x180068829  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180068830  mov     edx, 1EDh; void *
0x180068835  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006883b  mov     rbx, [rbp+28h]
0x18006883f  mov     rcx, rdi; string
0x180068842  call    cs:__imp_WindowsIsStringEmpty
0x180068848  test    eax, eax
0x18006884a  jz      short loc_180068867
0x18006884c  mov     r9d, 80070057h; char *
0x180068852  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180068859  mov     edx, 1EEh; void *
0x18006885e  mov     rcx, rbx; this
0x180068861  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068867  mov     dword ptr [r14], 0
0x18006886e  lea     rbx, [r15+40h]
0x180068872  mov     rcx, rbx; lpCriticalSection
0x180068875  call    cs:__imp_EnterCriticalSection
0x18006887b  mov     [rbp+var_10], rbx
0x18006887f  xor     edx, edx; length
0x180068881  mov     rcx, rdi; string
0x180068884  call    cs:__imp_WindowsGetStringRawBuffer
0x18006888a  mov     r12, rax
0x18006888d  mov     rbx, [r15+68h]
0x180068891  mov     rbx, [rbx]
0x180068894  cmp     rbx, [r15+68h]
0x180068898  jz      loc_1800689CD
0x18006889e  mov     [rbp+string], 0
0x1800688a6  mov     rsi, [rbx+28h]
0x1800688aa  mov     rax, [rsi]
0x1800688ad  mov     rdi, [rax+38h]
0x1800688b1  xor     ecx, ecx; string
0x1800688b3  call    cs:__imp_WindowsDeleteString
0x1800688b9  mov     [rbp+string], 0
0x1800688c1  lea     rdx, [rbp+string]
0x1800688c5  mov     rcx, rsi
0x1800688c8  mov     rax, rdi
0x1800688cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688d0  mov     rcx, [rbp+28h]; this
0x1800688d4  test    eax, eax
0x1800688d6  js      loc_180068A1E
0x1800688dc  xor     edx, edx; length
0x1800688de  mov     rcx, [rbp+string]; string
0x1800688e2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800688e8  test    rax, rax
0x1800688eb  jz      short loc_180068901
0x1800688ed  mov     rdx, rax; String2
0x1800688f0  mov     rcx, r12; String1
0x1800688f3  call    cs:__imp__wcsicmp
0x1800688f9  test    eax, eax
0x1800688fb  jz      loc_1800689BC
0x180068901  mov     [rbp+arg_10], 0
0x180068909  mov     rsi, [rbx+28h]
0x18006890d  mov     rax, [rsi]
0x180068910  mov     rdi, [rax+40h]
0x180068914  xor     ecx, ecx; string
0x180068916  call    cs:__imp_WindowsDeleteString
0x18006891c  mov     [rbp+arg_10], 0
0x180068924  lea     rdx, [rbp+arg_10]
0x180068928  mov     rcx, rsi
0x18006892b  mov     rax, rdi
0x18006892e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068933  mov     rcx, [rbp+28h]; this
0x180068937  test    eax, eax
0x180068939  js      loc_180068A09
0x18006893f  xor     edx, edx; length
0x180068941  mov     rcx, [rbp+arg_10]; string
0x180068945  call    cs:__imp_WindowsGetStringRawBuffer
0x18006894b  test    rax, rax
0x18006894e  jz      short loc_180068964
0x180068950  mov     rdx, rax; String2
0x180068953  mov     rcx, r12; String1
0x180068956  call    cs:__imp__wcsicmp
0x18006895c  test    eax, eax
0x18006895e  jz      loc_1800689EF
0x180068964  mov     rcx, [rbp+arg_10]; string
0x180068968  call    cs:__imp_WindowsDeleteString
0x18006896e  mov     [rbp+arg_10], 0
0x180068976  mov     rcx, [rbp+string]; string
0x18006897a  call    cs:__imp_WindowsDeleteString
0x180068980  cmp     byte ptr [rbx+19h], 0
0x180068984  jnz     loc_180068894
0x18006898a  mov     rcx, [rbx+10h]
0x18006898e  cmp     byte ptr [rcx+19h], 0
0x180068992  jnz     short loc_18006899B
0x180068994  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(std::_Tree_node<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>,void *> *)
0x180068999  jmp     short loc_1800689B4
0x18006899b  mov     rax, [rbx+8]
0x18006899f  jmp     short loc_1800689AE
0x1800689a1  cmp     rbx, [rax+10h]
0x1800689a5  jnz     short loc_1800689B4
0x1800689a7  mov     rbx, rax
0x1800689aa  mov     rax, [rax+8]
0x1800689ae  cmp     byte ptr [rax+19h], 0
0x1800689b2  jz      short loc_1800689A1
0x1800689b4  mov     rbx, rax
0x1800689b7  jmp     loc_180068894
0x1800689bc  mov     eax, [rbx+20h]
0x1800689bf  mov     [r14], eax
0x1800689c2  mov     rcx, [rbp+string]; string
0x1800689c6  call    cs:__imp_WindowsDeleteString
0x1800689cc  nop
0x1800689cd  lea     rcx, [rbp+var_10]
0x1800689d1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800689d6  xor     eax, eax
0x1800689d8  mov     rbx, [rsp+30h+arg_0]
0x1800689dd  mov     rsi, [rsp+30h+arg_8]
0x1800689e2  add     rsp, 30h
0x1800689e6  pop     r15
0x1800689e8  pop     r14
0x1800689ea  pop     r12
0x1800689ec  pop     rdi
0x1800689ed  pop     rbp
0x1800689ee  retn
0x1800689ef  mov     eax, [rbx+20h]
0x1800689f2  mov     [r14], eax
0x1800689f5  mov     rcx, [rbp+arg_10]; string
0x1800689f9  call    cs:__imp_WindowsDeleteString
0x1800689ff  mov     [rbp+arg_10], 0
0x180068a07  jmp     short loc_1800689C2
0x180068a09  mov     r9d, eax; char *
0x180068a0c  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180068a13  mov     edx, 204h; void *
0x180068a18  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068a1e  mov     r9d, eax; char *
0x180068a21  lea     r8, aOnecoreDsSecur_60; "onecore\\ds\\security\\umstartup\\userm"...
0x180068a28  mov     edx, 1F8h; void *
0x180068a2d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
