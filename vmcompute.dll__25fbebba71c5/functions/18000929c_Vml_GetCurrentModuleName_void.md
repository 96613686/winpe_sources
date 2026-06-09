# Vml::GetCurrentModuleName(void)

- ea: `0x18000929c`
- end: `0x1800093bc`
- name: `?GetCurrentModuleName@Vml@@YAPEBGXZ`
- size: `288`
- prototype: `const unsigned __int16 *__fastcall(Vml *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a258`
- `0x18000df10`

## callees

- `0x180002f50`
- `0x18000929c`
- `0x18000d0ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009317`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009317`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800092d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800092d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009362`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009362`

## string_xrefs

- `0x1800093aa`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x180009398`: `onecore\vm\common\vml\VmModuleUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const unsigned __int16 *__fastcall Vml::GetCurrentModuleName(Vml *this)
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
  return Vml::Details::g_ModuleName;
}

```

## disassembly

```asm
0x18000929c  mov     [rsp+arg_0], rbx
0x1800092a1  mov     [rsp+arg_8], rsi
0x1800092a6  push    rdi
0x1800092a7  sub     rsp, 40h
0x1800092ab  mov     rax, cs:__security_cookie
0x1800092b2  xor     rax, rsp
0x1800092b5  mov     [rsp+48h+var_10], rax
0x1800092ba  xor     ebx, ebx
0x1800092bc  mov     [rsp+48h+fPending], ebx
0x1800092c0  xor     r9d, r9d; lpContext
0x1800092c3  lea     r8, [rsp+48h+fPending]; fPending
0x1800092c8  xor     edx, edx; dwFlags
0x1800092ca  lea     rsi, ?g_ModulePathInitOnce@Details@Vml@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE Vml::Details::g_ModulePathInitOnce
0x1800092d1  mov     rcx, rsi; lpInitOnce
0x1800092d4  call    cs:__imp___std_init_once_begin_initialize
0x1800092db  nop     dword ptr [rax+rax+00h]
0x1800092e0  mov     rcx, [rsp+48h]; this
0x1800092e5  test    eax, eax
0x1800092e7  jz      loc_1800093AA
0x1800092ed  cmp     [rsp+48h+fPending], ebx
0x1800092f1  jz      short loc_18000936E
0x1800092f3  mov     [rsp+48h+var_28], rsi
0x1800092f8  mov     [rsp+48h+var_20], 4
0x180009300  mov     r8d, 104h; nSize
0x180009306  lea     rdi, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x18000930d  mov     rdx, rdi; lpFilename
0x180009310  lea     rcx, __ImageBase; hModule
0x180009317  call    cs:__imp_GetModuleFileNameW
0x18000931e  nop     dword ptr [rax+rax+00h]
0x180009323  test    eax, eax
0x180009325  jz      short loc_180009393
0x180009327  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000932b  inc     rax
0x18000932e  cmp     [rdi+rax*2], bx
0x180009332  jnz     short loc_18000932B
0x180009334  test    rax, rax
0x180009337  jz      short loc_18000934F
0x180009339  cmp     word ptr [rdi+rax*2-2], 2Fh ; '/'
0x18000933f  jz      short loc_18000934F
0x180009341  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180009347  jz      short loc_18000934F
0x180009349  sub     rax, 1
0x18000934d  jnz     short loc_180009339
0x18000934f  lea     rax, [rdi+rax*2]
0x180009353  mov     cs:?g_ModuleName@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ModuleName
0x18000935a  xor     r8d, r8d; lpContext
0x18000935d  xor     edx, edx; dwFlags
0x18000935f  mov     rcx, rsi; lpInitOnce
0x180009362  call    cs:__imp_InitOnceComplete
0x180009369  nop     dword ptr [rax+rax+00h]
0x18000936e  mov     rax, cs:?g_ModuleName@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ModuleName
0x180009375  mov     rcx, [rsp+48h+var_10]
0x18000937a  xor     rcx, rsp; StackCookie
0x18000937d  call    __security_check_cookie
0x180009382  mov     rbx, [rsp+48h+arg_0]
0x180009387  mov     rsi, [rsp+48h+arg_8]
0x18000938c  add     rsp, 40h
0x180009390  pop     rdi
0x180009391  retn
0x180009393  mov     rcx, [rsp+48h]; this
0x180009398  lea     r8, aOnecoreVmCommo_10; "onecore\\vm\\common\\vml\\VmModuleUtils"...
0x18000939f  mov     edx, 30h ; '0'; void *
0x1800093a4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800093aa  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800093b1  mov     edx, 3BCh; void *
0x1800093b6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
