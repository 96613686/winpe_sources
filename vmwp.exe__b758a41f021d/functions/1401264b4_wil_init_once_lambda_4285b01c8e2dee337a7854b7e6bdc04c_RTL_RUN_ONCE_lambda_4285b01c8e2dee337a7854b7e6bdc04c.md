# wil::init_once<_lambda_4285b01c8e2dee337a7854b7e6bdc04c_>(_RTL_RUN_ONCE &,_lambda_4285b01c8e2dee337a7854b7e6bdc04c_)

- ea: `0x1401264b4`
- end: `0x1401265d1`
- name: `??$init_once@V_lambda_4285b01c8e2dee337a7854b7e6bdc04c_@@@wil@@YA_NAEAT_RTL_RUN_ONCE@@V_lambda_4285b01c8e2dee337a7854b7e6bdc04c_@@@Z`
- size: `285`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140127570`
- `0x14012aaf0`
- `0x14012b4fc`
- `0x14016bd88`

## callees

- `0x140083990`
- `0x14011ea40`
- `0x1401264b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140126541`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140126541`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1401264ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1401264ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401265a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1401265a1`

## string_xrefs

- `0x140126501`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`
- `0x140126556`: `onecore\vm\common\vml\VmModuleUtils.h`

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
0x1401264b4  mov     [rsp+arg_0], rbx
0x1401264b9  mov     [rsp+arg_8], rsi
0x1401264be  push    rdi
0x1401264bf  sub     rsp, 40h
0x1401264c3  mov     rax, cs:__security_cookie
0x1401264ca  xor     rax, rsp
0x1401264cd  mov     [rsp+48h+var_10], rax
0x1401264d2  xor     ebx, ebx
0x1401264d4  mov     [rsp+48h+fPending], ebx
0x1401264d8  xor     r9d, r9d; lpContext
0x1401264db  lea     r8, [rsp+48h+fPending]; fPending
0x1401264e0  xor     edx, edx; dwFlags
0x1401264e2  lea     rsi, ?g_ModulePathInitOnce@Details@Vml@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE Vml::Details::g_ModulePathInitOnce
0x1401264e9  mov     rcx, rsi; lpInitOnce
0x1401264ec  call    cs:__imp_InitOnceBeginInitialize
0x1401264f3  nop     dword ptr [rax+rax+00h]
0x1401264f8  mov     rcx, [rsp+48h]; this
0x1401264fd  test    eax, eax
0x1401264ff  jnz     short loc_140126513
0x140126501  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140126508  mov     edx, 3BCh; void *
0x14012650d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140126513  cmp     [rsp+48h+fPending], ebx
0x140126517  jz      loc_1401265B1
0x14012651d  mov     [rsp+48h+var_28], rsi
0x140126522  mov     [rsp+48h+var_20], 4
0x14012652a  mov     r8d, 104h; nSize
0x140126530  lea     rdi, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x140126537  mov     rdx, rdi; lpFilename
0x14012653a  lea     rcx, __ImageBase; hModule
0x140126541  call    cs:__imp_GetModuleFileNameW
0x140126548  nop     dword ptr [rax+rax+00h]
0x14012654d  test    eax, eax
0x14012654f  jnz     short loc_140126566
0x140126551  mov     rcx, [rsp+48h]; this
0x140126556  lea     r8, aOnecoreVmCommo_82; "onecore\\vm\\common\\vml\\VmModuleUtils"...
0x14012655d  lea     edx, [rax+30h]; void *
0x140126560  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140126566  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14012656a  inc     rdx
0x14012656d  cmp     [rdi+rdx*2], bx
0x140126571  jnz     short loc_14012656A
0x140126573  test    rdx, rdx
0x140126576  jz      short loc_14012658E
0x140126578  cmp     word ptr [rdi+rdx*2-2], 2Fh ; '/'
0x14012657e  jz      short loc_14012658E
0x140126580  cmp     word ptr [rdi+rdx*2-2], 5Ch ; '\'
0x140126586  jz      short loc_14012658E
0x140126588  sub     rdx, 1
0x14012658c  jnz     short loc_140126578
0x14012658e  lea     rdx, [rdi+rdx*2]
0x140126592  mov     cs:?g_ModuleName@Details@Vml@@3PEBGEB, rdx; ushort const * const Vml::Details::g_ModuleName
0x140126599  xor     r8d, r8d; lpContext
0x14012659c  xor     edx, edx; dwFlags
0x14012659e  mov     rcx, rsi; lpInitOnce
0x1401265a1  call    cs:__imp_InitOnceComplete
0x1401265a8  nop     dword ptr [rax+rax+00h]
0x1401265ad  mov     al, 1
0x1401265af  jmp     short loc_1401265B3
0x1401265b1  xor     al, al
0x1401265b3  mov     rcx, [rsp+48h+var_10]
0x1401265b8  xor     rcx, rsp; StackCookie
0x1401265bb  call    __security_check_cookie
0x1401265c0  mov     rbx, [rsp+48h+arg_0]
0x1401265c5  mov     rsi, [rsp+48h+arg_8]
0x1401265ca  add     rsp, 40h
0x1401265ce  pop     rdi
0x1401265cf  retn
```
