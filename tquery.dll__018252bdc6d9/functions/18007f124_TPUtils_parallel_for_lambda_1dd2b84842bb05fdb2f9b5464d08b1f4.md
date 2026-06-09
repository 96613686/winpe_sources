# TPUtils::parallel_for__lambda_1dd2b84842bb05fdb2f9b5464d08b1f4___

- ea: `0x18007f124`
- end: `0x18007f395`
- name: `TPUtils::parallel_for__lambda_1dd2b84842bb05fdb2f9b5464d08b1f4___`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1802474b0`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x180043d18`
- `0x18007f124`
- `0x18007f824`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007f2d4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007f2d4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007f29d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007f29d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007f340`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007f340`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007f2fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007f2fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007f1ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007f1ca`

## string_xrefs

- `0x18007f2b7`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18007f32b`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for__lambda_1dd2b84842bb05fdb2f9b5464d08b1f4___(
        __int64 a1,
        unsigned __int64 a2,
        __int128 *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  __int64 v9; // r13
  __int64 v10; // rsi
  unsigned __int64 v11; // rdi
  __int64 Catalog; // rax
  __int64 (__fastcall ***v13)(); // rdx
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v18; // r8
  const char *v19; // r9
  __int64 (__fastcall **v20)(); // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+38h] [rbp-C8h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  __int64 (__fastcall ***v23)(); // [rsp+68h] [rbp-98h]
  _BYTE pv[1104]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+4C0h] [rbp+3C0h]
  TPResultException *v26; // [rsp+4C8h] [rbp+3C8h]
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_31;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_31:
      lambda_1dd2b84842bb05fdb2f9b5464d08b1f4_::operator()(a3, (unsigned int)v5++, ProcessorCount);
    while ( v5 < a2 );
    return;
  }
  v7 = a2 / ProcessorCount;
  v8 = a2 % ProcessorCount;
  v9 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v9 = 1;
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
  v20 = off_1802C8410;
  v21 = *a3;
  v22 = *((_QWORD *)a3 + 2);
  v23 = &v20;
  TPUtils::_SParallelForContext::_SParallelForContext(pv, &v20, v11, Catalog);
  if ( v23 )
  {
    v13 = &v20;
    LOBYTE(v13) = v23 != &v20;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v23)[4])(v23, v13);
    v23 = 0;
  }
  if ( v11 )
  {
    v14 = 0;
    do
    {
      *(_QWORD *)&pv[16 * v14 + 80] = v5;
      v15 = v9 + 1;
      if ( !v10 )
        v15 = v9;
      v5 += v15;
      *(_QWORD *)&pv[16 * v14++ + 88] = v5;
      v16 = v10 - 1;
      if ( !v10 )
        v16 = 0;
      v10 = v16;
    }
    while ( v14 < v11 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v19);
  for ( ; v11; --v11 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_1dd2b84842bb05fdb2f9b5464d08b1f4_::operator()(a3, (unsigned int)v5++, v18);
  while ( v5 < a2 );
  WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
  if ( v25 > 0 )
  {
    if ( v26 )
      TPResultException::raise(v26);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      (const char *)0x8000FFFFLL,
      (int)ThreadpoolWork);
  }
  CloseThreadpoolWork(ThreadpoolWork);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)pv);
}

```

## disassembly

```asm
0x18007f124  mov     [rsp-8+arg_0], rbx
0x18007f129  mov     [rsp-8+arg_18], rsi
0x18007f12e  push    rbp
0x18007f12f  push    rdi
0x18007f130  push    r13
0x18007f132  push    r14
0x18007f134  push    r15
0x18007f136  lea     rbp, [rsp-3F0h]
0x18007f13e  sub     rsp, 4F0h
0x18007f145  mov     rax, cs:__security_cookie
0x18007f14c  xor     rax, rsp
0x18007f14f  mov     [rbp+410h+var_30], rax
0x18007f156  mov     r15, r8
0x18007f159  mov     r14, rdx
0x18007f15c  xor     ebx, ebx
0x18007f15e  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18007f163  mov     r8, rax
0x18007f166  lea     r9d, [rbx+1]
0x18007f16a  cmp     rax, r9
0x18007f16d  jz      loc_18007F353
0x18007f173  cmp     r14, r9
0x18007f176  jbe     loc_18007F353
0x18007f17c  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x18007f182  cmp     eax, 19h
0x18007f185  ja      loc_18007F358
0x18007f18b  xor     edx, edx
0x18007f18d  mov     rax, r14
0x18007f190  div     r8
0x18007f193  mov     rdi, rdx
0x18007f196  mov     r13, rax
0x18007f199  test    rax, rax
0x18007f19c  cmovz   r13, r9
0x18007f1a0  mov     rcx, rax
0x18007f1a3  neg     rcx
0x18007f1a6  sbb     rsi, rsi
0x18007f1a9  and     rsi, rdx
0x18007f1ac  test    rax, rax
0x18007f1af  cmovnz  rdi, r8
0x18007f1b3  sub     rdi, r9
0x18007f1b6  xor     r9d, r9d; Context
0x18007f1b9  xor     r8d, r8d; Parameter
0x18007f1bc  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18007f1c3  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18007f1ca  call    cs:__imp_InitOnceExecuteOnce
0x18007f1d0  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x18007f1d6  jz      short loc_18007F1DF
0x18007f1d8  call    PerUserCatalogNameForCorruption__GetCatalog
0x18007f1dd  jmp     short loc_18007F1E1
0x18007f1df  xor     eax, eax
0x18007f1e1  lea     rcx, off_1802C8410
0x18007f1e8  mov     [rsp+510h+var_4E0], rcx
0x18007f1ed  movups  xmm0, xmmword ptr [r15]
0x18007f1f1  movups  [rsp+510h+var_4D8], xmm0
0x18007f1f6  movsd   xmm1, qword ptr [r15+10h]
0x18007f1fc  movsd   [rsp+510h+var_4C8], xmm1
0x18007f202  lea     rcx, [rsp+510h+var_4E0]
0x18007f207  mov     [rsp+510h+var_4A8], rcx
0x18007f20c  mov     r9, rax
0x18007f20f  mov     r8, rdi
0x18007f212  lea     rdx, [rsp+510h+var_4E0]
0x18007f217  lea     rcx, [rsp+510h+pv]
0x18007f21c  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x18007f221  nop
0x18007f222  mov     rcx, [rsp+510h+var_4A8]
0x18007f227  test    rcx, rcx
0x18007f22a  jz      short loc_18007F24C
0x18007f22c  mov     rax, [rcx]
0x18007f22f  lea     rdx, [rsp+510h+var_4E0]
0x18007f234  cmp     rcx, rdx
0x18007f237  setnz   dl
0x18007f23a  mov     rax, [rax+20h]
0x18007f23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f243  mov     [rsp+510h+var_4A8], 0
0x18007f24c  test    rdi, rdi
0x18007f24f  jz      short loc_18007F287
0x18007f251  xor     edx, edx
0x18007f253  mov     rcx, rdx
0x18007f256  add     rcx, rcx
0x18007f259  mov     [rbp+rcx*8+410h+var_450], rbx
0x18007f25e  lea     rax, [r13+1]
0x18007f262  test    rsi, rsi
0x18007f265  cmovz   rax, r13
0x18007f269  add     rbx, rax
0x18007f26c  mov     [rbp+rcx*8+410h+var_448], rbx
0x18007f271  inc     rdx
0x18007f274  lea     rax, [rsi-1]
0x18007f278  test    rsi, rsi
0x18007f27b  cmovz   rax, rsi
0x18007f27f  mov     rsi, rax
0x18007f282  cmp     rdx, rdi
0x18007f285  jb      short loc_18007F253
0x18007f287  mov     [rsp+510h+var_4E8], 1
0x18007f28e  xor     r8d, r8d; pcbe
0x18007f291  lea     rdx, [rsp+510h+pv]; pv
0x18007f296  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18007f29d  call    cs:__imp_CreateThreadpoolWork
0x18007f2a3  mov     rsi, rax
0x18007f2a6  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x18007f2ab  test    rax, rax
0x18007f2ae  jnz     short loc_18007F2C7
0x18007f2b0  mov     rcx, [rbp+418h]; this
0x18007f2b7  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18007f2be  lea     edx, [rax+7Eh]; void *
0x18007f2c1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007f2c7  mov     byte ptr [rsp+510h+var_4E8+1], 1
0x18007f2cc  test    rdi, rdi
0x18007f2cf  jz      short loc_18007F2E0
0x18007f2d1  mov     rcx, rsi; pwk
0x18007f2d4  call    cs:__imp_SubmitThreadpoolWork
0x18007f2da  sub     rdi, 1
0x18007f2de  jnz     short loc_18007F2D1
0x18007f2e0  mov     edx, ebx
0x18007f2e2  mov     rcx, r15
0x18007f2e5  call    _lambda_1dd2b84842bb05fdb2f9b5464d08b1f4___operator__
0x18007f2ea  inc     rbx
0x18007f2ed  cmp     rbx, r14
0x18007f2f0  jb      short loc_18007F2E0
0x18007f2f2  mov     byte ptr [rsp+510h+var_4E8+1], 0
0x18007f2f7  xor     edx, edx; fCancelPendingCallbacks
0x18007f2f9  mov     rcx, rsi; pwk
0x18007f2fc  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18007f302  mov     eax, [rbp+410h+var_50]
0x18007f308  test    eax, eax
0x18007f30a  jle     short loc_18007F33D
0x18007f30c  mov     rcx, [rbp+410h+var_48]; this
0x18007f313  test    rcx, rcx
0x18007f316  jz      short loc_18007F31E
0x18007f318  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x18007f31e  mov     rcx, [rbp+418h]; this
0x18007f325  mov     r9d, 8000FFFFh; char *
0x18007f32b  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18007f332  mov     edx, 194h; void *
0x18007f337  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007f33d  mov     rcx, rsi; pwk
0x18007f340  call    cs:__imp_CloseThreadpoolWork
0x18007f346  nop
0x18007f347  lea     rcx, [rsp+510h+pv]; this
0x18007f34c  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x18007f351  jmp     short loc_18007F36A
0x18007f353  test    r14, r14
0x18007f356  jz      short loc_18007F36A
0x18007f358  mov     edx, ebx
0x18007f35a  mov     rcx, r15
0x18007f35d  call    _lambda_1dd2b84842bb05fdb2f9b5464d08b1f4___operator__
0x18007f362  inc     rbx
0x18007f365  cmp     rbx, r14
0x18007f368  jb      short loc_18007F358
0x18007f36a  mov     rcx, [rbp+410h+var_30]
0x18007f371  xor     rcx, rsp; StackCookie
0x18007f374  call    __security_check_cookie
0x18007f379  lea     r11, [rsp+510h+var_20]
0x18007f381  mov     rbx, [r11+30h]
0x18007f385  mov     rsi, [r11+48h]
0x18007f389  mov     rsp, r11
0x18007f38c  pop     r15
0x18007f38e  pop     r14
0x18007f390  pop     r13
0x18007f392  pop     rdi
0x18007f393  pop     rbp
0x18007f394  retn
```
