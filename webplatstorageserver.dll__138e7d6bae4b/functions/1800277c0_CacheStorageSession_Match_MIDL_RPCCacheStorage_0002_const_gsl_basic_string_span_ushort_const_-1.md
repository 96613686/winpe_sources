# CacheStorageSession::Match(__MIDL_RPCCacheStorage_0002 const &,gsl::basic_string_span<ushort const,-1> *)

- ea: `0x1800277c0`
- end: `0x180027961`
- name: `?Match@CacheStorageSession@@QEAA?AV?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@AEBU__MIDL_RPCCacheStorage_0002@@PEAV?$basic_string_span@$$CBG$0?0@gsl@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(_QWORD *, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800256a0`

## callees

- `0x180014bb0`
- `0x1800277c0`
- `0x180028c50`
- `0x180063d58`
- `0x1800c6010`

## import_xrefs

- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x180027830`
- `msvcp_win!_Unlock_shared_ptr_spin_lock` at `0x180027830`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x180027802`
- `msvcp_win!_Lock_shared_ptr_spin_lock` at `0x180027802`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180027952`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180027952`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180027882`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180027882`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002785e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002785e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002793d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002793d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180027895`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180027895`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180027877`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180027877`

## pseudocode

```c
__int64 __fastcall CacheStorageSession::Match(_QWORD *a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v8; // r12
  __int64 v9; // rbx
  __int64 v10; // rax
  union _RTL_RUN_ONCE *v11; // rdi
  volatile signed __int32 *v12; // rbx
  char v13; // al
  PINIT_ONCE InitOnce[2]; // [rsp+40h] [rbp-68h] BYREF
  __int128 v16; // [rsp+50h] [rbp-58h] BYREF
  _QWORD Parameter[2]; // [rsp+60h] [rbp-48h] BYREF
  __int128 v18; // [rsp+70h] [rbp-38h] BYREF
  char *v19; // [rsp+B0h] [rbp+8h] BYREF

  SequentialExecutionEnforcer::Start(a1[4], &v19);
  v8 = *(_QWORD *)(*a1 + 8LL);
  v9 = a1[6];
  _Lock_shared_ptr_spin_lock();
  *(_OWORD *)InitOnce = 0;
  v10 = *(_QWORD *)(v9 + 24);
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
  InitOnce[0] = *(PINIT_ONCE *)(v9 + 16);
  InitOnce[1] = *(PINIT_ONCE *)(v9 + 24);
  _Unlock_shared_ptr_spin_lock();
  v11 = InitOnce[0];
  if ( InitOnce[0] )
  {
    Parameter[0] = InitOnce;
    Parameter[1] = v9;
    v18 = 0;
    __ExceptionPtrCreate(&v18);
    InitOnceExecuteOnce(v11, lambda_60775d1107346de3b9cc64a0a0339a26_::_lambda_invoker_cdecl_, Parameter, 0);
    if ( __ExceptionPtrToBool(&v18) )
    {
      v16 = 0;
      __ExceptionPtrCopy(&v16, &v18);
      __ExceptionPtrRethrow(&v16);
LABEL_14:
      MicrosoftTelemetryAssertTriggeredNoArgs();
      return a2;
    }
    __ExceptionPtrDestroy(&v18);
  }
  v12 = (volatile signed __int32 *)InitOnce[1];
  if ( InitOnce[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&InitOnce[1][1], 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  CacheStorageActiveReference::MatchRequest(v8, a2, (_DWORD)a1 + 64, a3, a4);
  if ( v19 )
  {
    v13 = *v19;
    *v19 = 0;
    if ( !v13 )
      goto LABEL_14;
  }
  return a2;
}

```

## disassembly

```asm
0x1800277c0  mov     [rsp+arg_8], rbx
0x1800277c5  mov     [rsp+arg_10], rbp
0x1800277ca  push    rsi
0x1800277cb  push    rdi
0x1800277cc  push    r12
0x1800277ce  push    r14
0x1800277d0  push    r15
0x1800277d2  sub     rsp, 80h
0x1800277d9  mov     rbp, r9
0x1800277dc  mov     r15, r8
0x1800277df  mov     rsi, rdx
0x1800277e2  mov     r14, rcx
0x1800277e5  lea     rdx, [rsp+0A8h+arg_0]
0x1800277ed  mov     rcx, [rcx+20h]
0x1800277f1  call    ?Start@SequentialExecutionEnforcer@@QEAA?AVInProgressExecution@1@XZ; SequentialExecutionEnforcer::Start(void)
0x1800277f6  nop
0x1800277f7  mov     rax, [r14]
0x1800277fa  mov     r12, [rax+8]
0x1800277fe  mov     rbx, [r14+30h]
0x180027802  call    cs:__imp__Lock_shared_ptr_spin_lock
0x180027808  xorps   xmm0, xmm0
0x18002780b  movdqu  xmmword ptr [rsp+0A8h+InitOnce], xmm0
0x180027811  mov     rax, [rbx+18h]
0x180027815  test    rax, rax
0x180027818  jz      short loc_18002781E
0x18002781a  lock inc dword ptr [rax+8]
0x18002781e  mov     rax, [rbx+10h]
0x180027822  mov     [rsp+0A8h+InitOnce], rax
0x180027827  mov     rax, [rbx+18h]
0x18002782b  mov     [rsp+0A8h+InitOnce+8], rax
0x180027830  call    cs:__imp__Unlock_shared_ptr_spin_lock
0x180027836  nop
0x180027837  mov     rdi, [rsp+0A8h+InitOnce]
0x18002783c  test    rdi, rdi
0x18002783f  jz      short loc_18002789C
0x180027841  lea     rax, [rsp+0A8h+InitOnce]
0x180027846  mov     [rsp+0A8h+Parameter], rax
0x18002784b  mov     [rsp+0A8h+var_40], rbx
0x180027850  xorps   xmm0, xmm0
0x180027853  movdqu  [rsp+0A8h+var_38], xmm0
0x180027859  lea     rcx, [rsp+0A8h+var_38]
0x18002785e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180027864  nop
0x180027865  xor     r9d, r9d; Context
0x180027868  lea     r8, [rsp+0A8h+Parameter]; Parameter
0x18002786d  lea     rdx, _lambda_60775d1107346de3b9cc64a0a0339a26____lambda_invoker_cdecl_; InitFn
0x180027874  mov     rcx, rdi; InitOnce
0x180027877  call    cs:__imp_InitOnceExecuteOnce
0x18002787d  lea     rcx, [rsp+0A8h+var_38]
0x180027882  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180027888  test    al, al
0x18002788a  jnz     loc_18002792A
0x180027890  lea     rcx, [rsp+0A8h+var_38]
0x180027895  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002789b  nop
0x18002789c  mov     rbx, [rsp+0A8h+InitOnce+8]
0x1800278a1  test    rbx, rbx
0x1800278a4  jz      short loc_1800278DE
0x1800278a6  mov     edi, 0FFFFFFFFh
0x1800278ab  mov     eax, edi
0x1800278ad  lock xadd [rbx+8], eax
0x1800278b2  cmp     eax, 1
0x1800278b5  jnz     short loc_1800278DE
0x1800278b7  mov     rax, [rbx]
0x1800278ba  mov     rcx, rbx
0x1800278bd  mov     rax, [rax]
0x1800278c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278c5  lock xadd [rbx+0Ch], edi
0x1800278ca  cmp     edi, 1
0x1800278cd  jnz     short loc_1800278DE
0x1800278cf  mov     rax, [rbx]
0x1800278d2  mov     rcx, rbx
0x1800278d5  mov     rax, [rax+8]
0x1800278d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278de  lea     r8, [r14+40h]
0x1800278e2  mov     [rsp+0A8h+var_88], rbp
0x1800278e7  mov     r9, r15
0x1800278ea  mov     rdx, rsi
0x1800278ed  mov     rcx, r12
0x1800278f0  call    ?MatchRequest@CacheStorageActiveReference@@QEAA?AV?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@AEBV?$shared_ptr@UIDatabaseTable@EseHelper@@@3@AEBU__MIDL_RPCCacheStorage_0002@@PEAV?$basic_string_span@$$CBG$0?0@gsl@@@Z; CacheStorageActiveReference::MatchRequest(std::shared_ptr<EseHelper::IDatabaseTable> const &,__MIDL_RPCCacheStorage_0002 const &,gsl::basic_string_span<ushort const,-1> *)
0x1800278f5  nop
0x1800278f6  mov     rcx, [rsp+0A8h+arg_0]
0x1800278fe  test    rcx, rcx
0x180027901  jz      short loc_18002790B
0x180027903  xor     eax, eax
0x180027905  xchg    al, [rcx]
0x180027907  test    al, al
0x180027909  jz      short loc_180027959
0x18002790b  mov     rax, rsi
0x18002790e  lea     r11, [rsp+0A8h+var_28]
0x180027916  mov     rbx, [r11+38h]
0x18002791a  mov     rbp, [r11+40h]
0x18002791e  mov     rsp, r11
0x180027921  pop     r15
0x180027923  pop     r14
0x180027925  pop     r12
0x180027927  pop     rdi
0x180027928  pop     rsi
0x180027929  retn
0x18002792a  xorps   xmm0, xmm0
0x18002792d  movdqu  [rsp+0A8h+var_58], xmm0
0x180027933  lea     rdx, [rsp+0A8h+var_38]
0x180027938  lea     rcx, [rsp+0A8h+var_58]
0x18002793d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180027943  lea     rax, [rsp+0A8h+var_58]
0x180027948  mov     [rsp+0A8h+var_70], rax
0x18002794d  lea     rcx, [rsp+0A8h+var_58]
0x180027952  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180027958  nop
0x180027959  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002795e  jmp     short loc_18002790B
```
