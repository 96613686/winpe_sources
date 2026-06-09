# TPUtils::parallel_for<_lambda_3530836d53173db97dafa8696e97945a_>(unsigned __int64,unsigned __int64,_lambda_3530836d53173db97dafa8696e97945a_ const &)

- ea: `0x18007daf0`
- end: `0x18007dd5f`
- name: `??$parallel_for@V_lambda_3530836d53173db97dafa8696e97945a_@@@TPUtils@@SAX_K0AEBV_lambda_3530836d53173db97dafa8696e97945a_@@@Z`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18007d43c`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x180043d18`
- `0x18007cf04`
- `0x18007daf0`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007dc9e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007dc9e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007dc67`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007dc67`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007dd0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007dd0a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007dcc6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007dcc6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007db96`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007db96`

## string_xrefs

- `0x18007dc81`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18007dcf5`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
void __fastcall TPUtils::parallel_for<_lambda_3530836d53173db97dafa8696e97945a_>(
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
  void ***v13; // rdx
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v18; // r8
  const char *v19; // r9
  void **v20; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+38h] [rbp-C8h]
  __int128 v22; // [rsp+48h] [rbp-B8h]
  void ***v23; // [rsp+68h] [rbp-98h]
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
      _lambda_3530836d53173db97dafa8696e97945a_::operator()(a3, (unsigned int)v5++, ProcessorCount);
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
  v20 = &std::_Func_impl_no_alloc<_lambda_3530836d53173db97dafa8696e97945a_,void,unsigned __int64>::`vftable';
  v21 = *a3;
  v22 = a3[1];
  v23 = &v20;
  TPUtils::_SParallelForContext::_SParallelForContext(pv, &v20, v11, Catalog);
  if ( v23 )
  {
    v13 = &v20;
    LOBYTE(v13) = v23 != &v20;
    ((void (__fastcall *)(void ***, void ***))(*v23)[4])(v23, v13);
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
    _lambda_3530836d53173db97dafa8696e97945a_::operator()(a3, (unsigned int)v5++, v18);
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
0x18007daf0  mov     [rsp-8+arg_0], rbx
0x18007daf5  mov     [rsp-8+arg_18], rsi
0x18007dafa  push    rbp
0x18007dafb  push    rdi
0x18007dafc  push    r13
0x18007dafe  push    r14
0x18007db00  push    r15
0x18007db02  lea     rbp, [rsp-3F0h]
0x18007db0a  sub     rsp, 4F0h
0x18007db11  mov     rax, cs:__security_cookie
0x18007db18  xor     rax, rsp
0x18007db1b  mov     [rbp+410h+var_30], rax
0x18007db22  mov     r15, r8
0x18007db25  mov     r14, rdx
0x18007db28  xor     ebx, ebx
0x18007db2a  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18007db2f  mov     r8, rax
0x18007db32  lea     r9d, [rbx+1]
0x18007db36  cmp     rax, r9
0x18007db39  jz      loc_18007DD1D
0x18007db3f  cmp     r14, r9
0x18007db42  jbe     loc_18007DD1D
0x18007db48  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x18007db4e  cmp     eax, 19h
0x18007db51  ja      loc_18007DD22
0x18007db57  xor     edx, edx
0x18007db59  mov     rax, r14
0x18007db5c  div     r8
0x18007db5f  mov     rdi, rdx
0x18007db62  mov     r13, rax
0x18007db65  test    rax, rax
0x18007db68  cmovz   r13, r9
0x18007db6c  mov     rcx, rax
0x18007db6f  neg     rcx
0x18007db72  sbb     rsi, rsi
0x18007db75  and     rsi, rdx
0x18007db78  test    rax, rax
0x18007db7b  cmovnz  rdi, r8
0x18007db7f  sub     rdi, r9
0x18007db82  xor     r9d, r9d; Context
0x18007db85  xor     r8d, r8d; Parameter
0x18007db88  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18007db8f  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18007db96  call    cs:__imp_InitOnceExecuteOnce
0x18007db9c  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x18007dba2  jz      short loc_18007DBAB
0x18007dba4  call    PerUserCatalogNameForCorruption__GetCatalog
0x18007dba9  jmp     short loc_18007DBAD
0x18007dbab  xor     eax, eax
0x18007dbad  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_3530836d53173db97dafa8696e97945a_@@X_K@std@@6B@; const std::_Func_impl_no_alloc<_lambda_3530836d53173db97dafa8696e97945a_,void,unsigned __int64>::`vftable'
0x18007dbb4  mov     [rsp+510h+var_4E0], rcx
0x18007dbb9  movups  xmm0, xmmword ptr [r15]
0x18007dbbd  movups  [rsp+510h+var_4D8], xmm0
0x18007dbc2  movups  xmm1, xmmword ptr [r15+10h]
0x18007dbc7  movups  [rsp+510h+var_4C8], xmm1
0x18007dbcc  lea     rcx, [rsp+510h+var_4E0]
0x18007dbd1  mov     [rsp+510h+var_4A8], rcx
0x18007dbd6  mov     r9, rax
0x18007dbd9  mov     r8, rdi
0x18007dbdc  lea     rdx, [rsp+510h+var_4E0]
0x18007dbe1  lea     rcx, [rsp+510h+pv]
0x18007dbe6  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x18007dbeb  nop
0x18007dbec  mov     rcx, [rsp+510h+var_4A8]
0x18007dbf1  test    rcx, rcx
0x18007dbf4  jz      short loc_18007DC16
0x18007dbf6  mov     rax, [rcx]
0x18007dbf9  lea     rdx, [rsp+510h+var_4E0]
0x18007dbfe  cmp     rcx, rdx
0x18007dc01  setnz   dl
0x18007dc04  mov     rax, [rax+20h]
0x18007dc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc0d  mov     [rsp+510h+var_4A8], 0
0x18007dc16  test    rdi, rdi
0x18007dc19  jz      short loc_18007DC51
0x18007dc1b  xor     edx, edx
0x18007dc1d  mov     rcx, rdx
0x18007dc20  add     rcx, rcx
0x18007dc23  mov     [rbp+rcx*8+410h+var_450], rbx
0x18007dc28  lea     rax, [r13+1]
0x18007dc2c  test    rsi, rsi
0x18007dc2f  cmovz   rax, r13
0x18007dc33  add     rbx, rax
0x18007dc36  mov     [rbp+rcx*8+410h+var_448], rbx
0x18007dc3b  inc     rdx
0x18007dc3e  lea     rax, [rsi-1]
0x18007dc42  test    rsi, rsi
0x18007dc45  cmovz   rax, rsi
0x18007dc49  mov     rsi, rax
0x18007dc4c  cmp     rdx, rdi
0x18007dc4f  jb      short loc_18007DC1D
0x18007dc51  mov     [rsp+510h+var_4E8], 1
0x18007dc58  xor     r8d, r8d; pcbe
0x18007dc5b  lea     rdx, [rsp+510h+pv]; pv
0x18007dc60  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18007dc67  call    cs:__imp_CreateThreadpoolWork
0x18007dc6d  mov     rsi, rax
0x18007dc70  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x18007dc75  test    rax, rax
0x18007dc78  jnz     short loc_18007DC91
0x18007dc7a  mov     rcx, [rbp+418h]; this
0x18007dc81  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18007dc88  lea     edx, [rax+7Eh]; void *
0x18007dc8b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007dc91  mov     byte ptr [rsp+510h+var_4E8+1], 1
0x18007dc96  test    rdi, rdi
0x18007dc99  jz      short loc_18007DCAA
0x18007dc9b  mov     rcx, rsi; pwk
0x18007dc9e  call    cs:__imp_SubmitThreadpoolWork
0x18007dca4  sub     rdi, 1
0x18007dca8  jnz     short loc_18007DC9B
0x18007dcaa  mov     edx, ebx
0x18007dcac  mov     rcx, r15
0x18007dcaf  call    ??R_lambda_3530836d53173db97dafa8696e97945a_@@QEBA@_K@Z; _lambda_3530836d53173db97dafa8696e97945a_::operator()(unsigned __int64)
0x18007dcb4  inc     rbx
0x18007dcb7  cmp     rbx, r14
0x18007dcba  jb      short loc_18007DCAA
0x18007dcbc  mov     byte ptr [rsp+510h+var_4E8+1], 0
0x18007dcc1  xor     edx, edx; fCancelPendingCallbacks
0x18007dcc3  mov     rcx, rsi; pwk
0x18007dcc6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18007dccc  mov     eax, [rbp+410h+var_50]
0x18007dcd2  test    eax, eax
0x18007dcd4  jle     short loc_18007DD07
0x18007dcd6  mov     rcx, [rbp+410h+var_48]; this
0x18007dcdd  test    rcx, rcx
0x18007dce0  jz      short loc_18007DCE8
0x18007dce2  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x18007dce8  mov     rcx, [rbp+418h]; this
0x18007dcef  mov     r9d, 8000FFFFh; char *
0x18007dcf5  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18007dcfc  mov     edx, 194h; void *
0x18007dd01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007dd07  mov     rcx, rsi; pwk
0x18007dd0a  call    cs:__imp_CloseThreadpoolWork
0x18007dd10  nop
0x18007dd11  lea     rcx, [rsp+510h+pv]; this
0x18007dd16  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x18007dd1b  jmp     short loc_18007DD34
0x18007dd1d  test    r14, r14
0x18007dd20  jz      short loc_18007DD34
0x18007dd22  mov     edx, ebx
0x18007dd24  mov     rcx, r15
0x18007dd27  call    ??R_lambda_3530836d53173db97dafa8696e97945a_@@QEBA@_K@Z; _lambda_3530836d53173db97dafa8696e97945a_::operator()(unsigned __int64)
0x18007dd2c  inc     rbx
0x18007dd2f  cmp     rbx, r14
0x18007dd32  jb      short loc_18007DD22
0x18007dd34  mov     rcx, [rbp+410h+var_30]
0x18007dd3b  xor     rcx, rsp; StackCookie
0x18007dd3e  call    __security_check_cookie
0x18007dd43  lea     r11, [rsp+510h+var_20]
0x18007dd4b  mov     rbx, [r11+30h]
0x18007dd4f  mov     rsi, [r11+48h]
0x18007dd53  mov     rsp, r11
0x18007dd56  pop     r15
0x18007dd58  pop     r14
0x18007dd5a  pop     r13
0x18007dd5c  pop     rdi
0x18007dd5d  pop     rbp
0x18007dd5e  retn
```
