# TPUtils::parallel_for__lambda_d7fd0d9ade6857f117a6ff719a4b3bf9___

- ea: `0x180180a14`
- end: `0x180180cbb`
- name: `TPUtils::parallel_for__lambda_d7fd0d9ade6857f117a6ff719a4b3bf9___`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18017a150`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x1800eaa2c`
- `0x1800ee964`
- `0x1800f2ee8`
- `0x180157c70`
- `0x180179e3c`
- `0x180180a14`
- `0x180188d90`
- `0x18019c834`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180af5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180180c23`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180180c23`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180180ad5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180180ad5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180180abc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180180abc`

## string_xrefs

- `0x180180c52`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x180180b16`: `onecoreuap\base\appmodel\Search\common\include\PerUserCatalogResetHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for__lambda_d7fd0d9ade6857f117a6ff719a4b3bf9___(
        __int64 a1,
        unsigned __int64 a2,
        __int128 *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r12
  __int64 v10; // r13
  unsigned __int64 v11; // r14
  LPVOID Value; // rsi
  bool v13; // r12
  signed int LastError; // eax
  unsigned __int64 v15; // rdx
  __int64 (__fastcall ***v16)(); // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  struct _TP_CALLBACK_ENVIRON_V3 *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  PTP_WORK pwk; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+39h] [rbp-C7h]
  __int64 (__fastcall **v24)(); // [rsp+40h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h]
  __int128 v26; // [rsp+58h] [rbp-A8h]
  __int128 v27; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall ***v28)(); // [rsp+78h] [rbp-88h]
  _BYTE v29[1104]; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+4D0h] [rbp+3D0h]
  TPResultException *v31; // [rsp+4D8h] [rbp+3D8h]
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_37;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_37:
      lambda_d7fd0d9ade6857f117a6ff719a4b3bf9_::operator()(a3, (unsigned int)v5++, ProcessorCount);
    while ( v5 < a2 );
    return;
  }
  v7 = a2 / ProcessorCount;
  v8 = a2 % ProcessorCount;
  v9 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v9 = 1;
  pwk = (PTP_WORK)v9;
  v10 = (a2 % ProcessorCount) & -(__int64)(v7 != 0);
  if ( v7 )
    v8 = ProcessorCount;
  v11 = v8 - 1;
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( !g_isPerUserCatalogEnabled || PerUserCatalogNameForCorruption::g_tlsIndex == -1 )
  {
    Value = 0;
  }
  else
  {
    Value = TlsGetValue(PerUserCatalogNameForCorruption::g_tlsIndex);
    v13 = !Value && GetLastError();
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( v13 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\PerUserCatalogResetHelper.h",
        (const char *)(unsigned int)LastError,
        (int)v20);
    v9 = (__int64)pwk;
  }
  v24 = off_1802C8B00;
  v25 = *a3;
  v26 = a3[1];
  v27 = a3[2];
  v28 = &v24;
  TPUtils::_SParallelForContext::_SParallelForContext(v29, &v24, v11, Value);
  if ( v28 )
  {
    v16 = &v24;
    LOBYTE(v16) = v28 != &v24;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v28)[4])(v28, v16);
    v28 = 0;
  }
  if ( v11 )
  {
    v15 = 0;
    do
    {
      *(_QWORD *)&v29[16 * v15 + 80] = v5;
      v17 = v9 + 1;
      if ( !v10 )
        v17 = v9;
      v5 += v17;
      *(_QWORD *)&v29[16 * v15++ + 88] = v5;
      v18 = v10 - 1;
      if ( !v10 )
        v18 = 0;
      v10 = v18;
    }
    while ( v15 < v11 );
  }
  pwk = 0;
  CThreadPoolWork::Init((CThreadPoolWork *)&pwk, v15, TPUtils::_ParallelForCallback, v29, v20);
  CThreadPoolWork::SubmitThreadpoolWork((CThreadPoolWork *)&pwk, v11);
  do
    lambda_d7fd0d9ade6857f117a6ff719a4b3bf9_::operator()(a3, (unsigned int)v5++, v19);
  while ( v5 < a2 );
  v23 = 0;
  WaitForThreadpoolWorkCallbacks(pwk, 0);
  if ( v30 > 0 )
  {
    if ( v31 )
      TPResultException::raise(v31);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      (const char *)0x8000FFFFLL,
      v21);
  }
  CThreadPoolWork::~CThreadPoolWork(&pwk);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)v29);
}

```

## disassembly

```asm
0x180180a14  mov     [rsp-8+arg_0], rbx
0x180180a19  push    rbp
0x180180a1a  push    rsi
0x180180a1b  push    rdi
0x180180a1c  push    r12
0x180180a1e  push    r13
0x180180a20  push    r14
0x180180a22  push    r15
0x180180a24  lea     rbp, [rsp-400h]
0x180180a2c  sub     rsp, 500h
0x180180a33  mov     rax, cs:__security_cookie
0x180180a3a  xor     rax, rsp
0x180180a3d  mov     [rbp+430h+var_40], rax
0x180180a44  mov     r15, r8
0x180180a47  mov     rdi, rdx
0x180180a4a  xor     ebx, ebx
0x180180a4c  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x180180a51  mov     r8, rax
0x180180a54  lea     esi, [rbx+1]
0x180180a57  cmp     rax, rsi
0x180180a5a  jz      loc_180180C7A
0x180180a60  cmp     rdi, rsi
0x180180a63  jbe     loc_180180C7A
0x180180a69  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x180180a6f  cmp     eax, 19h
0x180180a72  ja      loc_180180C7F
0x180180a78  xor     edx, edx
0x180180a7a  mov     rax, rdi
0x180180a7d  div     r8
0x180180a80  mov     r14, rdx
0x180180a83  mov     r12, rax
0x180180a86  test    rax, rax
0x180180a89  cmovz   r12, rsi
0x180180a8d  mov     [rsp+530h+pwk], r12
0x180180a92  mov     rcx, rax
0x180180a95  neg     rcx
0x180180a98  sbb     r13, r13
0x180180a9b  and     r13, rdx
0x180180a9e  test    rax, rax
0x180180aa1  cmovnz  r14, r8
0x180180aa5  sub     r14, rsi
0x180180aa8  xor     r9d, r9d; Context
0x180180aab  xor     r8d, r8d; Parameter
0x180180aae  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180180ab5  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180180abc  call    cs:__imp_InitOnceExecuteOnce
0x180180ac2  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x180180ac8  jz      short loc_180180B2E
0x180180aca  mov     ecx, cs:?g_tlsIndex@PerUserCatalogNameForCorruption@@3KA; dwTlsIndex
0x180180ad0  cmp     ecx, 0FFFFFFFFh
0x180180ad3  jz      short loc_180180B2E
0x180180ad5  call    cs:__imp_TlsGetValue
0x180180adb  mov     rsi, rax
0x180180ade  test    rax, rax
0x180180ae1  jnz     short loc_180180AF2
0x180180ae3  call    cs:__imp_GetLastError
0x180180ae9  test    eax, eax
0x180180aeb  jz      short loc_180180AF2
0x180180aed  mov     r12b, 1
0x180180af0  jmp     short loc_180180AF5
0x180180af2  xor     r12b, r12b
0x180180af5  call    cs:__imp_GetLastError
0x180180afb  test    eax, eax
0x180180afd  jle     short loc_180180B07
0x180180aff  movzx   eax, ax
0x180180b02  or      eax, 80070000h
0x180180b07  mov     rcx, [rbp+438h]; this
0x180180b0e  test    r12b, r12b
0x180180b11  jz      short loc_180180B27
0x180180b13  mov     r9d, eax; char *
0x180180b16  lea     r8, aOnecoreuapBase_288; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180180b1d  mov     edx, 47h ; 'G'; void *
0x180180b22  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180180b27  mov     r12, [rsp+530h+pwk]
0x180180b2c  jmp     short loc_180180B30
0x180180b2e  xor     esi, esi
0x180180b30  lea     rax, off_1802C8B00
0x180180b37  mov     [rsp+530h+var_4F0], rax
0x180180b3c  movups  xmm0, xmmword ptr [r15]
0x180180b40  movups  [rsp+530h+var_4E8], xmm0
0x180180b45  movups  xmm1, xmmword ptr [r15+10h]
0x180180b4a  movups  [rsp+530h+var_4D8], xmm1
0x180180b4f  movups  xmm0, xmmword ptr [r15+20h]
0x180180b54  movups  [rsp+530h+var_4C8], xmm0
0x180180b59  lea     rax, [rsp+530h+var_4F0]
0x180180b5e  mov     [rsp+530h+var_4B8], rax
0x180180b63  mov     r9, rsi
0x180180b66  mov     r8, r14
0x180180b69  lea     rdx, [rsp+530h+var_4F0]
0x180180b6e  lea     rcx, [rbp+430h+var_4B0]
0x180180b72  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x180180b77  nop
0x180180b78  mov     rcx, [rsp+530h+var_4B8]
0x180180b7d  xor     esi, esi
0x180180b7f  test    rcx, rcx
0x180180b82  jz      short loc_180180BA0
0x180180b84  mov     rax, [rcx]
0x180180b87  lea     rdx, [rsp+530h+var_4F0]
0x180180b8c  cmp     rcx, rdx
0x180180b8f  setnz   dl
0x180180b92  mov     rax, [rax+20h]
0x180180b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180b9b  mov     [rsp+530h+var_4B8], rsi
0x180180ba0  test    r14, r14
0x180180ba3  jz      short loc_180180BDD
0x180180ba5  mov     rdx, rsi
0x180180ba8  mov     rcx, rdx
0x180180bab  add     rcx, rcx
0x180180bae  mov     [rbp+rcx*8+430h+var_460], rbx
0x180180bb3  lea     rax, [r12+1]
0x180180bb8  test    r13, r13
0x180180bbb  cmovz   rax, r12
0x180180bbf  add     rbx, rax
0x180180bc2  mov     [rbp+rcx*8+430h+var_458], rbx
0x180180bc7  inc     rdx; bool
0x180180bca  lea     rax, [r13-1]
0x180180bce  test    r13, r13
0x180180bd1  cmovz   rax, r13
0x180180bd5  mov     r13, rax
0x180180bd8  cmp     rdx, r14
0x180180bdb  jb      short loc_180180BA8
0x180180bdd  mov     [rsp+530h+pwk], rsi
0x180180be2  lea     r9, [rbp+430h+var_4B0]; void *
0x180180be6  lea     r8, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x180180bed  lea     rcx, [rsp+530h+pwk]; this
0x180180bf2  call    ?Init@CThreadPoolWork@@QEAAX_NP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z2PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; CThreadPoolWork::Init(bool,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *,_TP_CALLBACK_ENVIRON_V3 *)
0x180180bf7  nop
0x180180bf8  mov     rdx, r14; unsigned __int64
0x180180bfb  lea     rcx, [rsp+530h+pwk]; this
0x180180c00  call    ?SubmitThreadpoolWork@CThreadPoolWork@@QEAAX_K@Z; CThreadPoolWork::SubmitThreadpoolWork(unsigned __int64)
0x180180c05  mov     edx, ebx
0x180180c07  mov     rcx, r15
0x180180c0a  call    _lambda_d7fd0d9ade6857f117a6ff719a4b3bf9___operator__
0x180180c0f  inc     rbx
0x180180c12  cmp     rbx, rdi
0x180180c15  jb      short loc_180180C05
0x180180c17  mov     [rsp+530h+var_4F7], sil
0x180180c1c  xor     edx, edx; fCancelPendingCallbacks
0x180180c1e  mov     rcx, [rsp+530h+pwk]; pwk
0x180180c23  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180180c29  mov     eax, [rbp+430h+var_60]
0x180180c2f  test    eax, eax
0x180180c31  jle     short loc_180180C64
0x180180c33  mov     rcx, [rbp+430h+var_58]; this
0x180180c3a  test    rcx, rcx
0x180180c3d  jz      short loc_180180C45
0x180180c3f  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x180180c45  mov     rcx, [rbp+438h]; this
0x180180c4c  mov     r9d, 8000FFFFh; char *
0x180180c52  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180180c59  mov     edx, 194h; void *
0x180180c5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180180c64  lea     rcx, [rsp+530h+pwk]; this
0x180180c69  call    ??1CThreadPoolWork@@QEAA@XZ; CThreadPoolWork::~CThreadPoolWork(void)
0x180180c6e  nop
0x180180c6f  lea     rcx, [rbp+430h+var_4B0]; this
0x180180c73  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x180180c78  jmp     short loc_180180C91
0x180180c7a  test    rdi, rdi
0x180180c7d  jz      short loc_180180C91
0x180180c7f  mov     edx, ebx
0x180180c81  mov     rcx, r15
0x180180c84  call    _lambda_d7fd0d9ade6857f117a6ff719a4b3bf9___operator__
0x180180c89  add     rbx, rsi
0x180180c8c  cmp     rbx, rdi
0x180180c8f  jb      short loc_180180C7F
0x180180c91  mov     rcx, [rbp+430h+var_40]
0x180180c98  xor     rcx, rsp; StackCookie
0x180180c9b  call    __security_check_cookie
0x180180ca0  mov     rbx, [rsp+530h+arg_0]
0x180180ca8  add     rsp, 500h
0x180180caf  pop     r15
0x180180cb1  pop     r14
0x180180cb3  pop     r13
0x180180cb5  pop     r12
0x180180cb7  pop     rdi
0x180180cb8  pop     rsi
0x180180cb9  pop     rbp
0x180180cba  retn
```
