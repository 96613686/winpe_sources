# TPUtils::parallel_for__lambda_e849ed5c46c2f59d8b7181792306942c___

- ea: `0x18002d358`
- end: `0x18002d62b`
- name: `TPUtils::parallel_for__lambda_e849ed5c46c2f59d8b7181792306942c___`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002b3c0`

## callees

- `0x18002cc2c`
- `0x18002d358`
- `0x18002dcc0`
- `0x180038f08`
- `0x180043ccc`
- `0x180043d18`
- `0x1800e9c64`
- `0x18010b920`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002d541`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002d541`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002d51d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002d51d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002d581`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002d581`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002d56e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002d56e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002d40f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002d40f`

## string_xrefs

- `0x18002d5fa`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18002d613`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall TPUtils::parallel_for__lambda_e849ed5c46c2f59d8b7181792306942c___(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  __int64 Catalog; // r13
  char *v12; // rsi
  _QWORD *v13; // r15
  __int64 v14; // r12
  __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  char v26; // [rsp+50h] [rbp-B0h] BYREF
  char *v27; // [rsp+88h] [rbp-78h]
  _BYTE pv[56]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+C8h] [rbp-38h]
  int v30; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v31; // [rsp+D8h] [rbp-28h]
  _QWORD v32[128]; // [rsp+E0h] [rbp-20h] BYREF
  int v33; // [rsp+4E0h] [rbp+3E0h]
  TPResultException *v34; // [rsp+4E8h] [rbp+3E8h]
  __int64 v35; // [rsp+4F0h] [rbp+3F0h]
  __int64 v36; // [rsp+4F8h] [rbp+3F8h]
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+448h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_32;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_32:
      lambda_e849ed5c46c2f59d8b7181792306942c_::operator()(a3, (unsigned int)v5++, ProcessorCount);
    while ( v5 < a2 );
    return;
  }
  v7 = a2 / ProcessorCount;
  v8 = a2 % ProcessorCount;
  v9 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v9 = 1;
  v23 = v9;
  v24 = v8 & -(__int64)(v7 != 0);
  if ( v7 )
    v8 = ProcessorCount;
  v10 = v8 - 1;
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
    Catalog = PerUserCatalogNameForCorruption::GetCatalog();
  else
    Catalog = 0;
  v12 = (char *)std::_Global_new_std::_Func_impl_no_alloc__lambda_e849ed5c46c2f59d8b7181792306942c__void_unsigned___int64___lambda_e849ed5c46c2f59d8b7181792306942c__const___(a3);
  v27 = v12;
  v29 = 0;
  if ( v12 )
    v29 = (**(__int64 (__fastcall ***)(char *, _BYTE *))v12)(v12, pv);
  v30 = 0;
  v31 = v10;
  v13 = v32;
  v14 = 64;
  do
  {
    std::pair<unsigned __int64,unsigned __int64>::pair<unsigned __int64,unsigned __int64>(v13);
    v13 += 2;
    --v14;
  }
  while ( v14 );
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = Catalog;
  if ( v12 )
  {
    LOBYTE(v15) = v12 != &v26;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v12 + 32LL))(v12, v15);
  }
  if ( v10 )
  {
    v16 = 0;
    v17 = v24;
    do
    {
      v32[2 * v16] = v5;
      v18 = v23 + 1;
      if ( !v17 )
        v18 = v23;
      v5 += v18;
      v32[2 * v16++ + 1] = v5;
      v19 = v17 - 1;
      if ( !v17 )
        v19 = 0;
      v17 = v19;
    }
    while ( v16 < v10 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v22);
  for ( ; v10; --v10 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_e849ed5c46c2f59d8b7181792306942c_::operator()(a3, (unsigned int)v5++, v21);
  while ( v5 < a2 );
  WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
  if ( v33 > 0 )
  {
    if ( !v34 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
        (const char *)0x8000FFFFLL,
        (int)ThreadpoolWork);
    TPResultException::raise(v34);
  }
  CloseThreadpoolWork(ThreadpoolWork);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)pv);
}

```

## disassembly

```asm
0x18002d358  mov     [rsp-8+arg_0], rbx
0x18002d35d  push    rbp
0x18002d35e  push    rsi
0x18002d35f  push    rdi
0x18002d360  push    r12
0x18002d362  push    r13
0x18002d364  push    r14
0x18002d366  push    r15
0x18002d368  lea     rbp, [rsp-410h]
0x18002d370  sub     rsp, 510h
0x18002d377  mov     rax, cs:__security_cookie
0x18002d37e  xor     rax, rsp
0x18002d381  mov     [rbp+440h+var_40], rax
0x18002d388  mov     rsi, r8
0x18002d38b  mov     [rsp+540h+var_500], r8
0x18002d390  mov     r14, rdx
0x18002d393  xor     r15d, r15d
0x18002d396  mov     ebx, r15d
0x18002d399  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18002d39e  mov     r8, rax
0x18002d3a1  lea     r12d, [r15+1]
0x18002d3a5  cmp     rax, r12
0x18002d3a8  jz      loc_18002D5C8
0x18002d3ae  cmp     r14, r12
0x18002d3b1  jbe     loc_18002D5C8
0x18002d3b7  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x18002d3bd  cmp     eax, 19h
0x18002d3c0  ja      loc_18002D5CD
0x18002d3c6  xor     edx, edx
0x18002d3c8  mov     rax, r14
0x18002d3cb  div     r8
0x18002d3ce  mov     rdi, rdx
0x18002d3d1  mov     rcx, rax
0x18002d3d4  test    rax, rax
0x18002d3d7  cmovz   rcx, r12
0x18002d3db  mov     [rsp+540h+var_510], rcx
0x18002d3e0  mov     rcx, rax
0x18002d3e3  neg     rcx
0x18002d3e6  sbb     rdx, rdx
0x18002d3e9  and     rdx, rdi
0x18002d3ec  mov     [rsp+540h+var_508], rdx
0x18002d3f1  test    rax, rax
0x18002d3f4  cmovnz  rdi, r8
0x18002d3f8  sub     rdi, r12
0x18002d3fb  xor     r9d, r9d; Context
0x18002d3fe  xor     r8d, r8d; Parameter
0x18002d401  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002d408  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18002d40f  call    cs:__imp_InitOnceExecuteOnce
0x18002d415  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, r15b; bool g_isPerUserCatalogEnabled
0x18002d41c  jnz     loc_18002D5BB
0x18002d422  mov     r13d, r15d
0x18002d425  mov     [rbp+440h+var_4B8], r15
0x18002d429  mov     rcx, rsi
0x18002d42c  call    std___Global_new_std___Func_impl_no_alloc__lambda_e849ed5c46c2f59d8b7181792306942c__void_unsigned___int64___lambda_e849ed5c46c2f59d8b7181792306942c__const___
0x18002d431  mov     rsi, rax
0x18002d434  mov     [rbp+440h+var_4B8], rax
0x18002d438  lea     rax, [rbp+440h+pv]
0x18002d43c  mov     qword ptr [rsp+540h+var_520], rax
0x18002d441  mov     [rbp+440h+var_478], r15
0x18002d445  test    rsi, rsi
0x18002d448  jz      short loc_18002D460
0x18002d44a  mov     rcx, [rsi]
0x18002d44d  mov     rax, [rcx]
0x18002d450  lea     rdx, [rbp+440h+pv]
0x18002d454  mov     rcx, rsi
0x18002d457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d45c  mov     [rbp+440h+var_478], rax
0x18002d460  mov     [rbp+440h+var_470], r15d
0x18002d464  mov     [rbp+440h+var_468], rdi
0x18002d468  lea     r15, [rbp+440h+var_460]
0x18002d46c  mov     r12d, 40h ; '@'
0x18002d472  mov     rcx, r15; void *
0x18002d475  call    ??$?0_K_K$0A@@?$pair@_K_K@std@@QEAA@XZ; std::pair<unsigned __int64,unsigned __int64>::pair<unsigned __int64,unsigned __int64>(void)
0x18002d47a  add     r15, 10h
0x18002d47e  sub     r12, 1
0x18002d482  jnz     short loc_18002D472
0x18002d484  xor     r15d, r15d
0x18002d487  mov     [rbp+440h+var_60], r15d
0x18002d48e  mov     [rbp+440h+var_58], r15
0x18002d495  mov     [rbp+440h+var_50], r15
0x18002d49c  mov     [rbp+440h+var_48], r13
0x18002d4a3  test    rsi, rsi
0x18002d4a6  jz      short loc_18002D4C2
0x18002d4a8  mov     rax, [rsi]
0x18002d4ab  lea     rcx, [rsp+540h+var_4F0]
0x18002d4b0  cmp     rsi, rcx
0x18002d4b3  setnz   dl
0x18002d4b6  mov     rcx, rsi
0x18002d4b9  mov     rax, [rax+20h]
0x18002d4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4c2  test    rdi, rdi
0x18002d4c5  jz      short loc_18002D508
0x18002d4c7  mov     rdx, r15
0x18002d4ca  mov     r10, [rsp+540h+var_510]
0x18002d4cf  mov     r8, [rsp+540h+var_508]
0x18002d4d4  mov     rcx, rdx
0x18002d4d7  add     rcx, rcx
0x18002d4da  mov     [rbp+rcx*8+440h+var_460], rbx
0x18002d4df  lea     rax, [r10+1]
0x18002d4e3  test    r8, r8
0x18002d4e6  cmovz   rax, r10
0x18002d4ea  add     rbx, rax
0x18002d4ed  mov     [rbp+rcx*8+440h+var_458], rbx
0x18002d4f2  inc     rdx
0x18002d4f5  lea     rax, [r8-1]
0x18002d4f9  test    r8, r8
0x18002d4fc  cmovz   rax, r8
0x18002d500  mov     r8, rax
0x18002d503  cmp     rdx, rdi
0x18002d506  jb      short loc_18002D4D4
0x18002d508  mov     [rsp+540h+var_518], 1
0x18002d50f  xor     r8d, r8d; pcbe
0x18002d512  lea     rdx, [rbp+440h+pv]; pv
0x18002d516  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002d51d  call    cs:__imp_CreateThreadpoolWork
0x18002d523  mov     rsi, rax
0x18002d526  mov     qword ptr [rsp+540h+var_520], rax; int
0x18002d52b  test    rax, rax
0x18002d52e  jz      loc_18002D60C
0x18002d534  mov     byte ptr [rsp+540h+var_518+1], 1
0x18002d539  test    rdi, rdi
0x18002d53c  jz      short loc_18002D54D
0x18002d53e  mov     rcx, rsi; pwk
0x18002d541  call    cs:__imp_SubmitThreadpoolWork
0x18002d547  sub     rdi, 1
0x18002d54b  jnz     short loc_18002D53E
0x18002d54d  mov     rdi, [rsp+540h+var_500]
0x18002d552  mov     edx, ebx
0x18002d554  mov     rcx, rdi
0x18002d557  call    _lambda_e849ed5c46c2f59d8b7181792306942c___operator__
0x18002d55c  inc     rbx
0x18002d55f  cmp     rbx, r14
0x18002d562  jb      short loc_18002D552
0x18002d564  mov     byte ptr [rsp+540h+var_518+1], r15b
0x18002d569  xor     edx, edx; fCancelPendingCallbacks
0x18002d56b  mov     rcx, rsi; pwk
0x18002d56e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002d574  mov     eax, [rbp+440h+var_60]
0x18002d57a  test    eax, eax
0x18002d57c  jg      short loc_18002D5E1
0x18002d57e  mov     rcx, rsi; pwk
0x18002d581  call    cs:__imp_CloseThreadpoolWork
0x18002d587  nop
0x18002d588  lea     rcx, [rbp+440h+pv]; this
0x18002d58c  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x18002d591  mov     rcx, [rbp+440h+var_40]
0x18002d598  xor     rcx, rsp; StackCookie
0x18002d59b  call    __security_check_cookie
0x18002d5a0  mov     rbx, [rsp+540h+arg_0]
0x18002d5a8  add     rsp, 510h
0x18002d5af  pop     r15
0x18002d5b1  pop     r14
0x18002d5b3  pop     r13
0x18002d5b5  pop     r12
0x18002d5b7  pop     rdi
0x18002d5b8  pop     rsi
0x18002d5b9  pop     rbp
0x18002d5ba  retn
0x18002d5bb  call    PerUserCatalogNameForCorruption__GetCatalog
0x18002d5c0  mov     r13, rax
0x18002d5c3  jmp     loc_18002D425
0x18002d5c8  test    r14, r14
0x18002d5cb  jz      short loc_18002D591
0x18002d5cd  mov     edx, ebx
0x18002d5cf  mov     rcx, rsi
0x18002d5d2  call    _lambda_e849ed5c46c2f59d8b7181792306942c___operator__
0x18002d5d7  add     rbx, r12
0x18002d5da  cmp     rbx, r14
0x18002d5dd  jb      short loc_18002D5CD
0x18002d5df  jmp     short loc_18002D591
0x18002d5e1  mov     rcx, [rbp+440h+var_58]; this
0x18002d5e8  test    rcx, rcx
0x18002d5eb  jnz     short loc_18002D625
0x18002d5ed  mov     rcx, [rbp+448h]; this
0x18002d5f4  mov     r9d, 8000FFFFh; char *
0x18002d5fa  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18002d601  mov     edx, 194h; void *
0x18002d606  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d60c  mov     rcx, [rbp+448h]; this
0x18002d613  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18002d61a  mov     edx, 7Eh ; '~'; void *
0x18002d61f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002d625  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
```
