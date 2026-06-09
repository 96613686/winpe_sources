# wil::init_once<_lambda_4285b01c8e2dee337a7854b7e6bdc04c_>(_RTL_RUN_ONCE &,_lambda_4285b01c8e2dee337a7854b7e6bdc04c_)

- ea: `0x14013a3d4`
- end: `0x14013a4f1`
- name: `??$init_once@V_lambda_4285b01c8e2dee337a7854b7e6bdc04c_@@@wil@@YA_NAEAT_RTL_RUN_ONCE@@V_lambda_4285b01c8e2dee337a7854b7e6bdc04c_@@@Z`
- size: `285`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14013b490`
- `0x14013ea10`
- `0x14013f41c`
- `0x14017d738`

## callees

- `0x14005b648`
- `0x140132960`
- `0x14013a3d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14013a461`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14013a461`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14013a4c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14013a4c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14013a40c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14013a40c`

## string_xrefs

- `0x14013a421`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`
- `0x14013a476`: `onecore\vm\common\vml\VmModuleUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char wil::init_once<_lambda_4285b01c8e2dee337a7854b7e6bdc04c_>()
{
  const char *v0; // r9
  const char *v1; // r9
  __int64 v2; // rdx
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  fPending = 0;
  if ( !InitOnceBeginInitialize(&Vml::Details::g_ModulePathInitOnce, 0, &fPending, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      v0);
  if ( !fPending )
    return 0;
  if ( !GetModuleFileNameW(&_ImageBase, &Vml::Details::g_ModulePath, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\vm\\common\\vml\\VmModuleUtils.h",
      v1);
  v2 = -1;
  do
    ++v2;
  while ( *(&Vml::Details::g_ModulePath + v2) );
  for ( ; v2; --v2 )
  {
    if ( *(&Vml::Details::g_ModulePath + v2 - 1) == 47 )
      break;
    if ( *(&Vml::Details::g_ModulePath + v2 - 1) == 92 )
      break;
  }
  Vml::Details::g_ModuleName = &Vml::Details::g_ModulePath + v2;
  InitOnceComplete(&Vml::Details::g_ModulePathInitOnce, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x14013a3d4  mov     [rsp+arg_0], rbx
0x14013a3d9  mov     [rsp+arg_8], rsi
0x14013a3de  push    rdi
0x14013a3df  sub     rsp, 40h
0x14013a3e3  mov     rax, cs:__security_cookie
0x14013a3ea  xor     rax, rsp
0x14013a3ed  mov     [rsp+48h+var_10], rax
0x14013a3f2  xor     ebx, ebx
0x14013a3f4  mov     [rsp+48h+fPending], ebx
0x14013a3f8  xor     r9d, r9d; lpContext
0x14013a3fb  lea     r8, [rsp+48h+fPending]; fPending
0x14013a400  xor     edx, edx; dwFlags
0x14013a402  lea     rsi, ?g_ModulePathInitOnce@Details@Vml@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE Vml::Details::g_ModulePathInitOnce
0x14013a409  mov     rcx, rsi; lpInitOnce
0x14013a40c  call    cs:__imp_InitOnceBeginInitialize
0x14013a413  nop     dword ptr [rax+rax+00h]
0x14013a418  mov     rcx, [rsp+48h]; this
0x14013a41d  test    eax, eax
0x14013a41f  jnz     short loc_14013A433
0x14013a421  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14013a428  mov     edx, 3BCh; void *
0x14013a42d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013a433  cmp     [rsp+48h+fPending], ebx
0x14013a437  jz      loc_14013A4D1
0x14013a43d  mov     [rsp+48h+var_28], rsi
0x14013a442  mov     [rsp+48h+var_20], 4
0x14013a44a  mov     r8d, 104h; nSize
0x14013a450  lea     rdi, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x14013a457  mov     rdx, rdi; lpFilename
0x14013a45a  lea     rcx, __ImageBase; hModule
0x14013a461  call    cs:__imp_GetModuleFileNameW
0x14013a468  nop     dword ptr [rax+rax+00h]
0x14013a46d  test    eax, eax
0x14013a46f  jnz     short loc_14013A486
0x14013a471  mov     rcx, [rsp+48h]; this
0x14013a476  lea     r8, aOnecoreVmCommo_82; "onecore\\vm\\common\\vml\\VmModuleUtils"...
0x14013a47d  lea     edx, [rax+30h]; void *
0x14013a480  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013a486  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14013a48a  inc     rdx
0x14013a48d  cmp     [rdi+rdx*2], bx
0x14013a491  jnz     short loc_14013A48A
0x14013a493  test    rdx, rdx
0x14013a496  jz      short loc_14013A4AE
0x14013a498  cmp     word ptr [rdi+rdx*2-2], 2Fh ; '/'
0x14013a49e  jz      short loc_14013A4AE
0x14013a4a0  cmp     word ptr [rdi+rdx*2-2], 5Ch ; '\'
0x14013a4a6  jz      short loc_14013A4AE
0x14013a4a8  sub     rdx, 1
0x14013a4ac  jnz     short loc_14013A498
0x14013a4ae  lea     rdx, [rdi+rdx*2]
0x14013a4b2  mov     cs:?g_ModuleName@Details@Vml@@3PEBGEB, rdx; ushort const * const Vml::Details::g_ModuleName
0x14013a4b9  xor     r8d, r8d; lpContext
0x14013a4bc  xor     edx, edx; dwFlags
0x14013a4be  mov     rcx, rsi; lpInitOnce
0x14013a4c1  call    cs:__imp_InitOnceComplete
0x14013a4c8  nop     dword ptr [rax+rax+00h]
0x14013a4cd  mov     al, 1
0x14013a4cf  jmp     short loc_14013A4D3
0x14013a4d1  xor     al, al
0x14013a4d3  mov     rcx, [rsp+48h+var_10]
0x14013a4d8  xor     rcx, rsp; StackCookie
0x14013a4db  call    __security_check_cookie
0x14013a4e0  mov     rbx, [rsp+48h+arg_0]
0x14013a4e5  mov     rsi, [rsp+48h+arg_8]
0x14013a4ea  add     rsp, 40h
0x14013a4ee  pop     rdi
0x14013a4ef  retn
```
