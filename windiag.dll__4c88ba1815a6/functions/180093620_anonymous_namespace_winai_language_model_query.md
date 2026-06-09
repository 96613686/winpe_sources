# _anonymous_namespace_::winai_language_model::query

- ea: `0x180093620`
- end: `0x1800939e7`
- name: `_anonymous_namespace_::winai_language_model::query`
- size: `967`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x180004510`
- `0x18000491c`
- `0x180005520`
- `0x18003aaa4`
- `0x18003ae28`
- `0x180046fe0`
- `0x1800911b0`
- `0x180091e88`
- `0x180092bf4`
- `0x180093620`
- `0x180094334`
- `0x18009d010`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x180093841`
- `msvcp_win!_Cnd_wait` at `0x180093841`
- `msvcp_win!_Mtx_unlock` at `0x180093862`
- `msvcp_win!_Mtx_unlock` at `0x180093930`
- `msvcp_win!_Mtx_unlock` at `0x180093862`
- `msvcp_win!_Mtx_unlock` at `0x180093930`
- `msvcp_win!_Mtx_lock` at `0x1800937c1`
- `msvcp_win!_Mtx_lock` at `0x1800938de`
- `msvcp_win!_Mtx_lock` at `0x1800937c1`
- `msvcp_win!_Mtx_lock` at `0x1800938de`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800937d0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800937eb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800938ed`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180093908`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800939b7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800937d0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800937eb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800938ed`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180093908`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800939b7`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800936e7`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800936e7`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009393e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009393e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800937aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180093876`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800937aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180093876`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18009388d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18009388d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180093884`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180093884`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180093793`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180093793`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall anonymous_namespace_::winai_language_model::query(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 options_const; // rax
  volatile signed __int32 *v8; // rbx
  __int64 v9; // rdi
  volatile signed __int32 *v10; // rsi
  __int64 *v11; // rax
  void *v12; // r12
  void *v13; // rsi
  struct _TP_WAIT *ThreadpoolWait; // r14
  struct _Cnd_internal_imp_t *v15; // rcx
  _QWORD *v16; // rdx
  const struct windiag::system_exception *v18; // rax
  struct _TP_WAIT *v19; // [rsp+30h] [rbp-D0h] BYREF
  void *v20; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24[4]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  _BYTE pExceptionObject[1072]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v29[7]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _QWORD *v30; // [rsp+4E8h] [rbp+3E8h]

  v25 = a2;
  v20 = operator new(0x598u);
  options_const = std::_Ref_count_obj2__anonymous_namespace_::winai_language_model::query_state_::_Ref_count_obj2__anonymous_namespace_::winai_language_model::query_state__std::basic_string_char_std::char_traits_char__std::allocator_char____const___winai::language_model::query_options_const___(
                    v20,
                    a3,
                    a4);
  v8 = (volatile signed __int32 *)options_const;
  v9 = options_const + 16;
  v26 = options_const + 16;
  v27 = options_const;
  v10 = (volatile signed __int32 *)(options_const + 8);
  if ( options_const )
    _InterlockedIncrement(v10);
  v21 = options_const + 16;
  v22 = options_const;
  v11 = (__int64 *)operator new(0x10u);
  *v11 = 0;
  v11[1] = 0;
  if ( v8 )
    _InterlockedIncrement(v10);
  *v11 = v9;
  v11[1] = (__int64)v8;
  v23 = _o__beginthreadex(
          0,
          0,
          std::thread::_Invoke_std::tuple__lambda_865271bad6951958d7d3efcd242d2632____0_,
          v11,
          0,
          v24,
          v11);
  if ( !v23 )
  {
    v24[0] = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_44;
  }
  v19 = 0;
  std::unique_ptr_std::tuple__lambda_865271bad6951958d7d3efcd242d2632____std::default_delete_std::tuple__lambda_865271bad6951958d7d3efcd242d2632_______::_unique_ptr_std::tuple__lambda_865271bad6951958d7d3efcd242d2632____std::default_delete_std::tuple__lambda_865271bad6951958d7d3efcd242d2632_______(&v19);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v10, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v29[0] = off_18009FB20;
  v29[1] = &v23;
  v30 = v29;
  v12 = (void *)*(unsigned int *)(a4 + 8);
  v13 = *(void **)a4;
  ThreadpoolWait = 0;
  v19 = 0;
  if ( v13 )
  {
    ThreadpoolWait = CreateThreadpoolWait(
                       lambda_8b7251ca2eba0419ad9395810a9604ce_::_lambda_invoker_cdecl___TP_CALLBACK_INSTANCE___void____TP_WAIT___unsigned_long_,
                       (PVOID)v9,
                       0);
    v19 = ThreadpoolWait;
    SetThreadpoolWait(ThreadpoolWait, v13, 0);
  }
  v21 = v9 + 120;
  LOBYTE(v22) = 0;
  if ( _Mtx_lock((_Mtx_t)(v9 + 120)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v9 + 196) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v9 + 196) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  LOBYTE(v22) = 1;
  while ( !*(_BYTE *)(v9 + 1392) )
  {
    if ( *(_BYTE *)(v9 + 1384) )
      goto LABEL_44;
    if ( *(_BYTE *)(v9 + 304) )
      break;
    v15 = (struct _Cnd_internal_imp_t *)(v9 + 200);
    if ( (_DWORD)v12 )
    {
      v20 = v12;
      if ( (unsigned int)std::condition_variable::wait_for<__int64,std::ratio<1,1>>(v15, &v21, &v20) == 1 )
        anonymous_namespace_::winai_language_model::query_state::cancel(v9);
    }
    else
    {
      _Cnd_wait(v15, (_Mtx_t)(v9 + 120));
    }
  }
  if ( *(_BYTE *)(v9 + 1384) )
  {
LABEL_44:
    v18 = (const struct windiag::system_exception *)std::optional<windiag::system_exception>::value(v9 + 312);
    windiag::system_exception::system_exception((windiag::system_exception *)pExceptionObject, v18);
    throw (windiag::system_exception *)pExceptionObject;
  }
  _Mtx_unlock((_Mtx_t)(v9 + 120));
  if ( ThreadpoolWait )
  {
    SetThreadpoolWait(ThreadpoolWait, 0, 0);
    WaitForThreadpoolWaitCallbacks(ThreadpoolWait, 1);
    CloseThreadpoolWait(ThreadpoolWait);
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
    if ( v30 )
    {
      v16 = v29;
      LOBYTE(v16) = v30 != v29;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v30 + 32LL))(v30, v16);
    }
  }
  v20 = (void *)(v9 + 120);
  if ( _Mtx_lock((_Mtx_t)(v9 + 120)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v9 + 196) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v9 + 196) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  *(_BYTE *)(a2 + 32) = 0;
  if ( *(_BYTE *)(v9 + 304) )
  {
    std::string::string(a2, v9 + 272);
    *(_BYTE *)(a2 + 32) = 1;
  }
  _Mtx_unlock((_Mtx_t)(v9 + 120));
  if ( v24[0] )
    _o_terminate();
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180093620  mov     [rsp-8+arg_0], rbx
0x180093625  push    rbp
0x180093626  push    rsi
0x180093627  push    rdi
0x180093628  push    r12
0x18009362a  push    r13
0x18009362c  push    r14
0x18009362e  push    r15
0x180093630  lea     rbp, [rsp-400h]
0x180093638  sub     rsp, 500h
0x18009363f  mov     rax, cs:__security_cookie
0x180093646  xor     rax, rsp
0x180093649  mov     [rbp+430h+var_40], rax
0x180093650  mov     r14, r9
0x180093653  mov     rbx, r8
0x180093656  mov     r15, rdx
0x180093659  mov     [rsp+530h+var_4C8], rdx
0x18009365e  xor     r13d, r13d
0x180093661  mov     ecx, 598h; Size
0x180093666  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009366b  mov     [rsp+530h+var_4F8], rax
0x180093670  mov     r8, r14
0x180093673  mov     rdx, rbx
0x180093676  mov     rcx, rax
0x180093679  call    std___Ref_count_obj2__anonymous_namespace___winai_language_model__query_state____Ref_count_obj2__anonymous_namespace___winai_language_model__query_state__std__basic_string_char_std__char_traits_char__std__allocator_char____const___winai__language_model__query_options_const___
0x18009367e  mov     rbx, rax
0x180093681  lea     rdi, [rax+10h]
0x180093685  mov     [rsp+530h+var_4C0], rdi
0x18009368a  mov     [rsp+530h+var_4B8], rax
0x18009368f  lea     rsi, [rax+8]
0x180093693  test    rax, rax
0x180093696  jz      short loc_18009369B
0x180093698  lock inc dword ptr [rsi]
0x18009369b  mov     [rsp+530h+var_4F0], rdi
0x1800936a0  mov     [rsp+530h+var_4E8], rbx
0x1800936a5  mov     ecx, 10h; Size
0x1800936aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800936af  mov     [rax], r13
0x1800936b2  mov     [rax+8], r13
0x1800936b6  test    rbx, rbx
0x1800936b9  jz      short loc_1800936BE
0x1800936bb  lock inc dword ptr [rsi]
0x1800936be  mov     [rax], rdi
0x1800936c1  mov     [rax+8], rbx
0x1800936c5  mov     [rsp+530h+var_500], rax
0x1800936ca  lea     rcx, [rsp+530h+var_4D8]
0x1800936cf  mov     [rsp+530h+var_508], rcx
0x1800936d4  mov     [rsp+530h+var_510], r13d
0x1800936d9  mov     r9, rax
0x1800936dc  lea     r8, std__thread___Invoke_std__tuple__lambda_865271bad6951958d7d3efcd242d2632____0_
0x1800936e3  xor     edx, edx
0x1800936e5  xor     ecx, ecx
0x1800936e7  call    cs:__imp__o__beginthreadex
0x1800936ed  mov     [rsp+530h+var_4E0], rax
0x1800936f2  test    rax, rax
0x1800936f5  jz      loc_1800939AD
0x1800936fb  mov     [rsp+530h+var_500], r13
0x180093700  lea     rcx, [rsp+530h+var_500]
0x180093705  call    std__unique_ptr_std__tuple__lambda_865271bad6951958d7d3efcd242d2632____std__default_delete_std__tuple__lambda_865271bad6951958d7d3efcd242d2632__________unique_ptr_std__tuple__lambda_865271bad6951958d7d3efcd242d2632____std__default_delete_std__tuple__lambda_865271bad6951958d7d3efcd242d2632_______
0x18009370a  nop
0x18009370b  or      r12d, 0FFFFFFFFh
0x18009370f  test    rbx, rbx
0x180093712  jz      short loc_18009374A
0x180093714  mov     eax, r12d
0x180093717  lock xadd [rsi], eax
0x18009371b  add     eax, r12d
0x18009371e  jnz     short loc_18009374A
0x180093720  mov     rax, [rbx]
0x180093723  mov     rcx, rbx
0x180093726  mov     rax, [rax]
0x180093729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009372e  mov     eax, r12d
0x180093731  lock xadd [rbx+0Ch], eax
0x180093736  add     eax, r12d
0x180093739  jnz     short loc_18009374A
0x18009373b  mov     rax, [rbx]
0x18009373e  mov     rcx, rbx
0x180093741  mov     rax, [rax+8]
0x180093745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009374a  lea     rax, off_18009FB20
0x180093751  mov     [rbp+430h+var_80], rax
0x180093758  lea     rax, [rsp+530h+var_4E0]
0x18009375d  mov     [rbp+430h+var_78], rax
0x180093764  lea     rax, [rbp+430h+var_80]
0x18009376b  mov     [rbp+430h+var_48], rax
0x180093772  mov     r12d, [r14+8]
0x180093776  mov     rsi, [r14]
0x180093779  mov     r14, r13
0x18009377c  mov     [rsp+530h+var_500], r13
0x180093781  test    rsi, rsi
0x180093784  jz      short loc_1800937B0
0x180093786  xor     r8d, r8d; pcbe
0x180093789  mov     rdx, rdi; pv
0x18009378c  lea     rcx, _lambda_8b7251ca2eba0419ad9395810a9604ce____lambda_invoker_cdecl___TP_CALLBACK_INSTANCE___void____TP_WAIT___unsigned_long_; pfnwa
0x180093793  call    cs:__imp_CreateThreadpoolWait
0x180093799  mov     r14, rax
0x18009379c  mov     [rsp+530h+var_500], rax
0x1800937a1  xor     r8d, r8d; pftTimeout
0x1800937a4  mov     rdx, rsi; h
0x1800937a7  mov     rcx, rax; pwa
0x1800937aa  call    cs:__imp_SetThreadpoolWait
0x1800937b0  lea     rsi, [rdi+78h]
0x1800937b4  mov     [rsp+530h+var_4F0], rsi
0x1800937b9  mov     byte ptr [rsp+530h+var_4E8], r13b
0x1800937be  mov     rcx, rsi; _Mtx_t
0x1800937c1  call    cs:__imp__Mtx_lock
0x1800937c7  test    eax, eax
0x1800937c9  jz      short loc_1800937D7
0x1800937cb  mov     ecx, 5
0x1800937d0  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800937d6  int     3; Trap to Debugger
0x1800937d7  mov     eax, [rsi+4Ch]
0x1800937da  cmp     eax, 7FFFFFFFh
0x1800937df  jnz     short loc_1800937F2
0x1800937e1  dec     eax
0x1800937e3  mov     [rsi+4Ch], eax
0x1800937e6  mov     ecx, 6
0x1800937eb  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800937f1  int     3; Trap to Debugger
0x1800937f2  mov     byte ptr [rsp+530h+var_4E8], 1
0x1800937f7  jmp     short loc_180093847
0x1800937f9  cmp     [rdi+568h], r13b
0x180093800  jnz     loc_1800939BE
0x180093806  cmp     [rdi+130h], r13b
0x18009380d  jnz     short loc_180093852
0x18009380f  lea     rcx, [rdi+0C8h]; _Cnd_t
0x180093816  test    r12d, r12d
0x180093819  jz      short loc_18009383E
0x18009381b  mov     [rsp+530h+var_4F8], r12
0x180093820  lea     r8, [rsp+530h+var_4F8]
0x180093825  lea     rdx, [rsp+530h+var_4F0]
0x18009382a  call    ??$wait_for@_JU?$ratio@$00$00@std@@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@1@@Z; std::condition_variable::wait_for<__int64,std::ratio<1,1>>(std::unique_lock<std::mutex> &,std::chrono::duration<__int64,std::ratio<1,1>> const &)
0x18009382f  cmp     eax, 1
0x180093832  jnz     short loc_180093847
0x180093834  mov     rcx, rdi
0x180093837  call    _anonymous_namespace___winai_language_model__query_state__cancel
0x18009383c  jmp     short loc_180093847
0x18009383e  mov     rdx, rsi; _Mtx_t
0x180093841  call    cs:__imp__Cnd_wait
0x180093847  mov     al, [rdi+570h]
0x18009384d  test    al, al
0x18009384f  nop
0x180093850  jz      short loc_1800937F9
0x180093852  cmp     [rdi+568h], r13b
0x180093859  jnz     loc_1800939BE
0x18009385f  mov     rcx, rsi; _Mtx_t
0x180093862  call    cs:__imp__Mtx_unlock
0x180093868  nop
0x180093869  test    r14, r14
0x18009386c  jz      short loc_180093894
0x18009386e  xor     r8d, r8d; pftTimeout
0x180093871  xor     edx, edx; h
0x180093873  mov     rcx, r14; pwa
0x180093876  call    cs:__imp_SetThreadpoolWait
0x18009387c  mov     edx, 1; fCancelPendingCallbacks
0x180093881  mov     rcx, r14; pwa
0x180093884  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18009388a  mov     rcx, r14; pwa
0x18009388d  call    cs:__imp_CloseThreadpoolWait
0x180093893  nop
0x180093894  mov     rcx, [rbp+430h+var_48]
0x18009389b  test    rcx, rcx
0x18009389e  jz      short loc_1800938D2
0x1800938a0  mov     rax, [rcx]
0x1800938a3  mov     rax, [rax+10h]
0x1800938a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800938ac  mov     rcx, [rbp+430h+var_48]
0x1800938b3  test    rcx, rcx
0x1800938b6  jz      short loc_1800938D2
0x1800938b8  mov     rax, [rcx]
0x1800938bb  lea     rdx, [rbp+430h+var_80]
0x1800938c2  cmp     rcx, rdx
0x1800938c5  setnz   dl
0x1800938c8  mov     rax, [rax+20h]
0x1800938cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800938d1  nop
0x1800938d2  lea     rsi, [rdi+78h]
0x1800938d6  mov     [rsp+530h+var_4F8], rsi
0x1800938db  mov     rcx, rsi; _Mtx_t
0x1800938de  call    cs:__imp__Mtx_lock
0x1800938e4  test    eax, eax
0x1800938e6  jz      short loc_1800938F4
0x1800938e8  mov     ecx, 5
0x1800938ed  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800938f3  int     3; Trap to Debugger
0x1800938f4  mov     eax, [rsi+4Ch]
0x1800938f7  cmp     eax, 7FFFFFFFh
0x1800938fc  jnz     short loc_18009390F
0x1800938fe  dec     eax
0x180093900  mov     [rsi+4Ch], eax
0x180093903  mov     ecx, 6
0x180093908  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18009390e  nop
0x18009390f  lea     rdx, [rdi+110h]
0x180093916  mov     [r15+20h], r13b
0x18009391a  cmp     [rdx+20h], r13b
0x18009391e  jz      short loc_18009392D
0x180093920  mov     rcx, r15
0x180093923  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180093928  mov     byte ptr [r15+20h], 1
0x18009392d  mov     rcx, rsi; _Mtx_t
0x180093930  call    cs:__imp__Mtx_unlock
0x180093936  nop
0x180093937  cmp     [rsp+530h+var_4D8], r13d
0x18009393c  jz      short loc_180093945
0x18009393e  call    cs:__imp__o_terminate
0x180093944  nop
0x180093945  test    rbx, rbx
0x180093948  jz      short loc_180093980
0x18009394a  or      edi, 0FFFFFFFFh
0x18009394d  mov     eax, edi
0x18009394f  lock xadd [rbx+8], eax
0x180093954  add     eax, edi
0x180093956  jnz     short loc_180093980
0x180093958  mov     rax, [rbx]
0x18009395b  mov     rcx, rbx
0x18009395e  mov     rax, [rax]
0x180093961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093966  mov     ecx, edi
0x180093968  lock xadd [rbx+0Ch], ecx
0x18009396d  add     ecx, edi
0x18009396f  jnz     short loc_180093980
0x180093971  mov     rcx, [rbx]
0x180093974  mov     rax, [rcx+8]
0x180093978  mov     rcx, rbx
0x18009397b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093980  mov     rax, r15
0x180093983  mov     rcx, [rbp+430h+var_40]
0x18009398a  xor     rcx, rsp; StackCookie
0x18009398d  call    __security_check_cookie
0x180093992  mov     rbx, [rsp+530h+arg_0]
0x18009399a  add     rsp, 500h
0x1800939a1  pop     r15
0x1800939a3  pop     r14
0x1800939a5  pop     r13
0x1800939a7  pop     r12
0x1800939a9  pop     rdi
0x1800939aa  pop     rsi
0x1800939ab  pop     rbp
0x1800939ac  retn
0x1800939ad  mov     [rsp+530h+var_4D8], r13d
0x1800939b2  mov     ecx, 6
0x1800939b7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800939bd  nop
0x1800939be  lea     rcx, [rdi+138h]
0x1800939c5  call    ?value@?$optional@Usystem_exception@windiag@@@std@@QEGAAAEAUsystem_exception@windiag@@XZ; std::optional<windiag::system_exception>::value(void)
0x1800939ca  mov     rdx, rax; struct windiag::system_exception *
0x1800939cd  lea     rcx, [rbp+430h+pExceptionObject]; this
0x1800939d1  call    ??0system_exception@windiag@@QEAA@AEBU01@@Z; windiag::system_exception::system_exception(windiag::system_exception const &)
0x1800939d6  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800939dd  lea     rcx, [rbp+430h+pExceptionObject]; pExceptionObject
0x1800939e1  call    _CxxThrowException_0
```
