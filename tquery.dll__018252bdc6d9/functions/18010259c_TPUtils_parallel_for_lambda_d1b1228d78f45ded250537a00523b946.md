# TPUtils::parallel_for__lambda_d1b1228d78f45ded250537a00523b946___

- ea: `0x18010259c`
- end: `0x1801027cf`
- name: `TPUtils::parallel_for__lambda_d1b1228d78f45ded250537a00523b946___`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180079af4`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x180043d18`
- `0x1800798f4`
- `0x18010259c`
- `0x180147154`
- `0x180157c70`
- `0x18016dc50`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102720`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102720`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801026fc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801026fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010275b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010275b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180102748`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180102748`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180102679`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180102679`

## string_xrefs

- `0x180102792`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x1801027b7`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall TPUtils::parallel_for__lambda_d1b1228d78f45ded250537a00523b946___(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r13
  unsigned __int64 v11; // rdi
  __int64 Catalog; // r15
  _BYTE *v13; // rsi
  __int64 v14; // rdx
  struct _TP_WORK *ThreadpoolWork; // rsi
  const char *v16; // r9
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  int v20[2]; // [rsp+20h] [rbp-E0h]
  _BYTE v21[56]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v22; // [rsp+68h] [rbp-98h]
  _BYTE pv[1104]; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+4C0h] [rbp+3C0h]
  TPResultException *v25; // [rsp+4C8h] [rbp+3C8h]
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_3;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_3:
      lambda_d1b1228d78f45ded250537a00523b946_::operator()(a3, (unsigned int)v5++);
    while ( v5 < a2 );
    return;
  }
  v7 = a2 / ProcessorCount;
  v8 = a2 % ProcessorCount;
  v9 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v9 = 1;
  *(_QWORD *)v20 = v9;
  v10 = (a2 % ProcessorCount) & -(__int64)(v7 != 0);
  if ( v7 )
    v8 = ProcessorCount;
  v11 = v8 - 1;
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
    Catalog = PerUserCatalogNameForCorruption::GetCatalog();
  else
    Catalog = 0;
  v13 = (_BYTE *)std::_Global_new_std::_Func_impl_no_alloc__lambda_d1b1228d78f45ded250537a00523b946__void_unsigned___int64___lambda_d1b1228d78f45ded250537a00523b946__const___(a3);
  v22 = v13;
  TPUtils::_SParallelForContext::_SParallelForContext(pv, v21, v11, Catalog);
  if ( v13 )
  {
    LOBYTE(v14) = v13 != v21;
    (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v13 + 32LL))(v13, v14);
  }
  if ( v11 )
  {
    v17 = 0;
    do
    {
      *(_QWORD *)&pv[16 * v17 + 80] = v5;
      v18 = *(_QWORD *)v20 + 1LL;
      if ( !v10 )
        v18 = *(_QWORD *)v20;
      v5 += v18;
      *(_QWORD *)&pv[16 * v17++ + 88] = v5;
      v19 = v10 - 1;
      if ( !v10 )
        v19 = 0;
      v10 = v19;
    }
    while ( v17 < v11 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v16);
  for ( ; v11; --v11 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_d1b1228d78f45ded250537a00523b946_::operator()(a3, (unsigned int)v5++);
  while ( v5 < a2 );
  WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
  if ( v24 > 0 )
  {
    if ( !v25 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
        (const char *)0x8000FFFFLL,
        (int)ThreadpoolWork);
    TPResultException::raise(v25);
  }
  CloseThreadpoolWork(ThreadpoolWork);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)pv);
}

```

## disassembly

```asm
0x18010259c  mov     [rsp-8+arg_0], rbx
0x1801025a1  push    rbp
0x1801025a2  push    rsi
0x1801025a3  push    rdi
0x1801025a4  push    r12
0x1801025a6  push    r13
0x1801025a8  push    r14
0x1801025aa  push    r15
0x1801025ac  lea     rbp, [rsp-3F0h]
0x1801025b4  sub     rsp, 4F0h
0x1801025bb  mov     rax, cs:__security_cookie
0x1801025c2  xor     rax, rsp
0x1801025c5  mov     [rbp+420h+var_40], rax
0x1801025cc  mov     r12, r8
0x1801025cf  mov     r14, rdx
0x1801025d2  xor     ebx, ebx
0x1801025d4  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x1801025d9  mov     r8, rax
0x1801025dc  lea     esi, [rbx+1]
0x1801025df  cmp     rax, rsi
0x1801025e2  jnz     short loc_180102625
0x1801025e4  test    r14, r14
0x1801025e7  jz      short loc_1801025FB
0x1801025e9  mov     edx, ebx
0x1801025eb  mov     rcx, r12
0x1801025ee  call    _lambda_d1b1228d78f45ded250537a00523b946___operator__
0x1801025f3  add     rbx, rsi
0x1801025f6  cmp     rbx, r14
0x1801025f9  jb      short loc_1801025E9
0x1801025fb  mov     rcx, [rbp+420h+var_40]
0x180102602  xor     rcx, rsp; StackCookie
0x180102605  call    __security_check_cookie
0x18010260a  mov     rbx, [rsp+520h+arg_0]
0x180102612  add     rsp, 4F0h
0x180102619  pop     r15
0x18010261b  pop     r14
0x18010261d  pop     r13
0x18010261f  pop     r12
0x180102621  pop     rdi
0x180102622  pop     rsi
0x180102623  pop     rbp
0x180102624  retn
0x180102625  cmp     r14, rsi
0x180102628  jbe     short loc_1801025E4
0x18010262a  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x180102630  cmp     eax, 19h
0x180102633  ja      short loc_1801025E9
0x180102635  xor     edx, edx
0x180102637  mov     rax, r14
0x18010263a  div     r8
0x18010263d  mov     rdi, rdx
0x180102640  mov     rcx, rax
0x180102643  test    rax, rax
0x180102646  cmovz   rcx, rsi
0x18010264a  mov     qword ptr [rsp+520h+var_500], rcx
0x18010264f  mov     rcx, rax
0x180102652  neg     rcx
0x180102655  sbb     r13, r13
0x180102658  and     r13, rdx
0x18010265b  test    rax, rax
0x18010265e  cmovnz  rdi, r8
0x180102662  sub     rdi, rsi
0x180102665  xor     r9d, r9d; Context
0x180102668  xor     r8d, r8d; Parameter
0x18010266b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180102672  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180102679  call    cs:__imp_InitOnceExecuteOnce
0x18010267f  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x180102685  jz      loc_180102771
0x18010268b  call    PerUserCatalogNameForCorruption__GetCatalog
0x180102690  mov     r15, rax
0x180102693  mov     [rsp+520h+var_4B8], rbx
0x180102698  mov     rcx, r12
0x18010269b  call    std___Global_new_std___Func_impl_no_alloc__lambda_d1b1228d78f45ded250537a00523b946__void_unsigned___int64___lambda_d1b1228d78f45ded250537a00523b946__const___
0x1801026a0  mov     rsi, rax
0x1801026a3  mov     [rsp+520h+var_4B8], rax
0x1801026a8  mov     r9, r15
0x1801026ab  mov     r8, rdi
0x1801026ae  lea     rdx, [rsp+520h+var_4F0]
0x1801026b3  lea     rcx, [rsp+520h+pv]
0x1801026b8  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x1801026bd  nop
0x1801026be  test    rsi, rsi
0x1801026c1  jz      short loc_1801026DD
0x1801026c3  mov     rax, [rsi]
0x1801026c6  lea     rcx, [rsp+520h+var_4F0]
0x1801026cb  cmp     rsi, rcx
0x1801026ce  setnz   dl
0x1801026d1  mov     rcx, rsi
0x1801026d4  mov     rax, [rax+20h]
0x1801026d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801026dd  test    rdi, rdi
0x1801026e0  jnz     loc_1801027A4
0x1801026e6  mov     [rsp+520h+var_4F8], 1
0x1801026ed  xor     r8d, r8d; pcbe
0x1801026f0  lea     rdx, [rsp+520h+pv]; pv
0x1801026f5  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801026fc  call    cs:__imp_CreateThreadpoolWork
0x180102702  mov     rsi, rax
0x180102705  mov     qword ptr [rsp+520h+var_500], rax; int
0x18010270a  test    rax, rax
0x18010270d  jz      loc_1801027B0
0x180102713  mov     byte ptr [rsp+520h+var_4F8+1], 1
0x180102718  test    rdi, rdi
0x18010271b  jz      short loc_18010272C
0x18010271d  mov     rcx, rsi; pwk
0x180102720  call    cs:__imp_SubmitThreadpoolWork
0x180102726  sub     rdi, 1
0x18010272a  jnz     short loc_18010271D
0x18010272c  mov     edx, ebx
0x18010272e  mov     rcx, r12
0x180102731  call    _lambda_d1b1228d78f45ded250537a00523b946___operator__
0x180102736  inc     rbx
0x180102739  cmp     rbx, r14
0x18010273c  jb      short loc_18010272C
0x18010273e  mov     byte ptr [rsp+520h+var_4F8+1], 0
0x180102743  xor     edx, edx; fCancelPendingCallbacks
0x180102745  mov     rcx, rsi; pwk
0x180102748  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18010274e  mov     eax, [rbp+420h+var_60]
0x180102754  test    eax, eax
0x180102756  jg      short loc_180102779
0x180102758  mov     rcx, rsi; pwk
0x18010275b  call    cs:__imp_CloseThreadpoolWork
0x180102761  nop
0x180102762  lea     rcx, [rsp+520h+pv]; this
0x180102767  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x18010276c  jmp     loc_1801025FB
0x180102771  xor     r15d, r15d
0x180102774  jmp     loc_180102693
0x180102779  mov     rcx, [rbp+420h+var_58]; this
0x180102780  test    rcx, rcx
0x180102783  jnz     short loc_1801027C9
0x180102785  mov     rcx, [rbp+428h]; this
0x18010278c  mov     r9d, 8000FFFFh; char *
0x180102792  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180102799  mov     edx, 194h; void *
0x18010279e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801027a4  xor     edx, edx
0x1801027a6  mov     r8, qword ptr [rsp+520h+var_500]
0x1801027ab  jmp     loc_1802BF0D6
0x1801027b0  mov     rcx, [rbp+428h]; this
0x1801027b7  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801027be  mov     edx, 7Eh ; '~'; void *
0x1801027c3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801027c9  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x1802bf0d6  mov     rcx, rdx
0x1802bf0d9  add     rcx, rcx
0x1802bf0dc  mov     [rbp+rcx*8+420h+var_460], rbx
0x1802bf0e1  lea     rax, [r8+1]
0x1802bf0e5  test    r13, r13
0x1802bf0e8  cmovz   rax, r8
0x1802bf0ec  add     rbx, rax
0x1802bf0ef  mov     [rbp+rcx*8+420h+var_458], rbx
0x1802bf0f4  inc     rdx
0x1802bf0f7  lea     rax, [r13-1]
0x1802bf0fb  test    r13, r13
0x1802bf0fe  cmovz   rax, r13
0x1802bf102  mov     r13, rax
0x1802bf105  cmp     rdx, rdi
0x1802bf108  jb      short loc_1802BF0D6
0x1802bf10a  jmp     loc_1801026E6
```
