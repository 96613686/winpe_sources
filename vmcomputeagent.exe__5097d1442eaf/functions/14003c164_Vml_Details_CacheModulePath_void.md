# Vml::Details::CacheModulePath(void)

- ea: `0x14003c164`
- end: `0x14003c26a`
- name: `?CacheModulePath@Details@Vml@@YAXXZ`
- size: `262`
- prototype: `void __fastcall(Vml::Details *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003c2e0`
- `0x14003c5c8`
- `0x14003c824`

## callees

- `0x140005360`
- `0x14000ddac`
- `0x14003c164`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14003c1d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14003c1d9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14003c19c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14003c19c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14003c21e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14003c21e`

## string_xrefs

- `0x14003c258`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x14003c246`: `onecore\vm\common\vml\VmModuleUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Vml::Details::CacheModulePath(Vml::Details *this)
{
  const char *v1; // r9
  const char *v2; // r9
  __int64 v3; // rax
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&Vml::Details::g_ModulePathInitOnce, 0, &fPending, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      v1);
  if ( fPending )
  {
    if ( !GetModuleFileNameW(&_ImageBase, &Vml::Details::g_ModulePath, 0x104u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModuleUtils.h",
        v2);
    v3 = -1;
    do
      ++v3;
    while ( *(&Vml::Details::g_ModulePath + v3) );
    for ( ; v3; --v3 )
    {
      if ( *(&Vml::Details::g_ModulePath + v3 - 1) == 47 )
        break;
      if ( *(&Vml::Details::g_ModulePath + v3 - 1) == 92 )
        break;
    }
    Vml::Details::g_ModuleName = &Vml::Details::g_ModulePath + v3;
    InitOnceComplete(&Vml::Details::g_ModulePathInitOnce, 0, 0);
  }
}

```

## disassembly

```asm
0x14003c164  mov     [rsp+arg_0], rbx
0x14003c169  mov     [rsp+arg_8], rsi
0x14003c16e  push    rdi
0x14003c16f  sub     rsp, 40h
0x14003c173  mov     rax, cs:__security_cookie
0x14003c17a  xor     rax, rsp
0x14003c17d  mov     [rsp+48h+var_10], rax
0x14003c182  xor     ebx, ebx
0x14003c184  mov     [rsp+48h+fPending], ebx
0x14003c188  xor     r9d, r9d; lpContext
0x14003c18b  lea     r8, [rsp+48h+fPending]; fPending
0x14003c190  xor     edx, edx; dwFlags
0x14003c192  lea     rsi, ?g_ModulePathInitOnce@Details@Vml@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE Vml::Details::g_ModulePathInitOnce
0x14003c199  mov     rcx, rsi; lpInitOnce
0x14003c19c  call    cs:__imp___std_init_once_begin_initialize
0x14003c1a2  mov     rcx, [rsp+48h]; this
0x14003c1a7  test    eax, eax
0x14003c1a9  jz      loc_14003C258
0x14003c1af  cmp     [rsp+48h+fPending], ebx
0x14003c1b3  jz      short loc_14003C224
0x14003c1b5  mov     [rsp+48h+var_28], rsi
0x14003c1ba  mov     [rsp+48h+var_20], 4
0x14003c1c2  mov     r8d, 104h; nSize
0x14003c1c8  lea     rdi, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x14003c1cf  mov     rdx, rdi; lpFilename
0x14003c1d2  lea     rcx, __ImageBase; hModule
0x14003c1d9  call    cs:__imp_GetModuleFileNameW
0x14003c1df  test    eax, eax
0x14003c1e1  jz      short loc_14003C241
0x14003c1e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003c1e7  inc     rax
0x14003c1ea  cmp     [rdi+rax*2], bx
0x14003c1ee  jnz     short loc_14003C1E7
0x14003c1f0  test    rax, rax
0x14003c1f3  jz      short loc_14003C20B
0x14003c1f5  cmp     word ptr [rdi+rax*2-2], 2Fh ; '/'
0x14003c1fb  jz      short loc_14003C20B
0x14003c1fd  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x14003c203  jz      short loc_14003C20B
0x14003c205  sub     rax, 1
0x14003c209  jnz     short loc_14003C1F5
0x14003c20b  lea     rax, [rdi+rax*2]
0x14003c20f  mov     cs:?g_ModuleName@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ModuleName
0x14003c216  xor     r8d, r8d; lpContext
0x14003c219  xor     edx, edx; dwFlags
0x14003c21b  mov     rcx, rsi; lpInitOnce
0x14003c21e  call    cs:__imp_InitOnceComplete
0x14003c224  mov     rcx, [rsp+48h+var_10]
0x14003c229  xor     rcx, rsp; StackCookie
0x14003c22c  call    __security_check_cookie
0x14003c231  mov     rbx, [rsp+48h+arg_0]
0x14003c236  mov     rsi, [rsp+48h+arg_8]
0x14003c23b  add     rsp, 40h
0x14003c23f  pop     rdi
0x14003c240  retn
0x14003c241  mov     rcx, [rsp+48h]; this
0x14003c246  lea     r8, aOnecoreVmCommo_11; "onecore\\vm\\common\\vml\\VmModuleUtils"...
0x14003c24d  mov     edx, 30h ; '0'; void *
0x14003c252  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14003c258  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14003c25f  mov     edx, 3BCh; void *
0x14003c264  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
