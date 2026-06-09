# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x1400197e0`
- end: `0x140019982`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005530`
- `0x14000e298`
- `0x1400197e0`
- `0x140019d60`
- `0x14001beb4`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1400198cd`
- `msvcp_win!_Mtx_unlock` at `0x14001995d`
- `msvcp_win!_Mtx_unlock` at `0x1400198cd`
- `msvcp_win!_Mtx_unlock` at `0x14001995d`
- `msvcp_win!_Mtx_lock` at `0x14001981c`
- `msvcp_win!_Mtx_lock` at `0x14001981c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001982b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140019847`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14001982b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x140019847`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1400198c3`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1400198c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Concurrency::details::_Task_impl<unsigned char>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // rsi
  int v9; // eax
  int v10; // edi
  int v11; // edi
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  _QWORD v15[7]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp-50h]

  v8 = a1 + 32;
  if ( _Mtx_lock((_Mtx_t)(a1 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v8 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v8 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v9 = *(_DWORD *)(a1 + 8);
  if ( !a3 )
  {
    if ( v9 != 3 && *(_DWORD *)(a1 + 8) != 4 && (*(_DWORD *)(a1 + 8) != 2 || a2) )
      goto LABEL_12;
LABEL_25:
    _Mtx_unlock((_Mtx_t)v8);
    return 0;
  }
  if ( v9 == 4 )
    goto LABEL_25;
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(a1 + 16, a5);
LABEL_12:
  if ( a2 )
  {
    *(_DWORD *)(a1 + 8) = 4;
    v10 = 1;
  }
  else
  {
    v10 = 0;
    if ( *(_DWORD *)(a1 + 8) == 1 )
      v10 = 2;
    *(_DWORD *)(a1 + 8) = 2;
    Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
  }
  _Mtx_unlock((_Mtx_t)v8);
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      v12 = *(_QWORD *)(a1 + 432);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  else
  {
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(a1 + 136));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v15[0] = &std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable';
      v15[1] = a1;
      v16 = v15;
      Concurrency::details::_ScheduleFuncWithAutoInline(v15, 16);
      if ( v16 )
      {
        v13 = v15;
        LOBYTE(v13) = v16 != v15;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v16 + 32LL))(v16, v13);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400197e0  push    rbx
0x1400197e2  push    rbp
0x1400197e3  push    rsi
0x1400197e4  push    rdi
0x1400197e5  push    r14
0x1400197e7  push    r15
0x1400197e9  sub     rsp, 88h
0x1400197f0  mov     rax, cs:__security_cookie
0x1400197f7  xor     rax, rsp
0x1400197fa  mov     [rsp+0B8h+var_48], rax
0x1400197ff  mov     bpl, r8b
0x140019802  mov     dil, dl
0x140019805  mov     rbx, rcx
0x140019808  mov     r14, [rsp+0B8h+arg_20]
0x140019810  lea     rsi, [rcx+20h]
0x140019814  mov     [rsp+0B8h+var_98], rsi
0x140019819  mov     rcx, rsi; _Mtx_t
0x14001981c  call    cs:__imp__Mtx_lock
0x140019822  test    eax, eax
0x140019824  jz      short loc_140019832
0x140019826  mov     ecx, 5
0x14001982b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140019831  int     3; Trap to Debugger
0x140019832  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x140019839  jnz     short loc_14001984E
0x14001983b  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x140019842  mov     ecx, 6
0x140019847  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14001984d  nop
0x14001984e  mov     r15d, 2
0x140019854  mov     eax, [rbx+8]
0x140019857  test    bpl, bpl
0x14001985a  jz      short loc_140019873
0x14001985c  cmp     eax, 4
0x14001985f  jz      loc_14001995A
0x140019865  lea     rcx, [rbx+10h]
0x140019869  mov     rdx, r14
0x14001986c  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x140019871  jmp     short loc_140019899
0x140019873  cmp     eax, 3
0x140019876  jz      loc_14001995A
0x14001987c  mov     eax, [rbx+8]
0x14001987f  cmp     eax, 4
0x140019882  jz      loc_14001995A
0x140019888  mov     eax, [rbx+8]
0x14001988b  cmp     eax, r15d
0x14001988e  jnz     short loc_140019899
0x140019890  test    dil, dil
0x140019893  jz      loc_14001995A
0x140019899  test    dil, dil
0x14001989c  jz      short loc_1400198AC
0x14001989e  mov     dword ptr [rbx+8], 4
0x1400198a5  mov     edi, 1
0x1400198aa  jmp     short loc_1400198CA
0x1400198ac  mov     eax, [rbx+8]
0x1400198af  xor     edi, edi
0x1400198b1  cmp     eax, 1
0x1400198b4  cmovz   edi, r15d
0x1400198b8  mov     [rbx+8], r15d
0x1400198bc  lea     rcx, [rbx+160h]
0x1400198c3  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x1400198c9  nop
0x1400198ca  mov     rcx, rsi; _Mtx_t
0x1400198cd  call    cs:__imp__Mtx_unlock
0x1400198d3  sub     edi, 1
0x1400198d6  jz      short loc_1400198F7
0x1400198d8  cmp     edi, 1
0x1400198db  jnz     short loc_140019956
0x1400198dd  mov     rcx, [rbx+1B0h]
0x1400198e4  test    rcx, rcx
0x1400198e7  jz      short loc_140019956
0x1400198e9  mov     rax, [rcx]
0x1400198ec  mov     rax, [rax+10h]
0x1400198f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400198f5  jmp     short loc_140019956
0x1400198f7  lea     rcx, [rbx+88h]; this
0x1400198fe  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x140019903  cmp     qword ptr [rbx+70h], 0
0x140019908  jz      short loc_140019956
0x14001990a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x140019911  mov     [rsp+0B8h+var_88], rax
0x140019916  mov     [rsp+0B8h+var_80], rbx
0x14001991b  lea     rax, [rsp+0B8h+var_88]
0x140019920  mov     [rsp+0B8h+var_50], rax
0x140019925  mov     edx, 10h
0x14001992a  lea     rcx, [rsp+0B8h+var_88]
0x14001992f  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x140019934  nop
0x140019935  mov     rcx, [rsp+0B8h+var_50]
0x14001993a  test    rcx, rcx
0x14001993d  jz      short loc_140019956
0x14001993f  mov     rax, [rcx]
0x140019942  lea     rdx, [rsp+0B8h+var_88]
0x140019947  cmp     rcx, rdx
0x14001994a  setnz   dl
0x14001994d  mov     rax, [rax+20h]
0x140019951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019956  mov     al, 1
0x140019958  jmp     short loc_140019965
0x14001995a  mov     rcx, rsi; _Mtx_t
0x14001995d  call    cs:__imp__Mtx_unlock
0x140019963  xor     al, al
0x140019965  mov     rcx, [rsp+0B8h+var_48]
0x14001996a  xor     rcx, rsp; StackCookie
0x14001996d  call    __security_check_cookie
0x140019972  add     rsp, 88h
0x140019979  pop     r15
0x14001997b  pop     r14
0x14001997d  pop     rdi
0x14001997e  pop     rsi
0x14001997f  pop     rbp
0x140019980  pop     rbx
0x140019981  retn
```
