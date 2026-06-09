# Concurrency::details::_Task_impl<uchar>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x1800586f0`
- end: `0x1800588f2`
- name: `?_CancelAndRunContinuations@?$_Task_impl@E@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800586f0`
- `0x180058b68`
- `0x180059eb4`
- `0x180086010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005872c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005874e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005872c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005874e`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180058828`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180058828`
- `msvcp_win!_Mtx_lock` at `0x180058717`
- `msvcp_win!_Mtx_lock` at `0x180058717`
- `msvcp_win!_Mtx_unlock` at `0x180058838`
- `msvcp_win!_Mtx_unlock` at `0x1800588ce`
- `msvcp_win!_Mtx_unlock` at `0x180058838`
- `msvcp_win!_Mtx_unlock` at `0x1800588ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Concurrency::details::_Task_impl<unsigned char>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v8; // rsi
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rdi
  int v13; // edi
  int v14; // edi
  __int64 v15; // rcx
  _QWORD *v16; // rdx
  _QWORD v18[7]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v19; // [rsp+58h] [rbp-20h]

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
  if ( a3 )
  {
    if ( v9 != 4 )
    {
      v10 = a5[1];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
      v11 = a5[1];
      *(_QWORD *)(a1 + 16) = *a5;
      v12 = *(volatile signed __int32 **)(a1 + 24);
      *(_QWORD *)(a1 + 24) = v11;
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      goto LABEL_17;
    }
LABEL_30:
    _Mtx_unlock((_Mtx_t)v8);
    return 0;
  }
  if ( v9 == 3 || *(_DWORD *)(a1 + 8) == 4 || *(_DWORD *)(a1 + 8) == 2 && !a2 )
    goto LABEL_30;
LABEL_17:
  if ( a2 )
  {
    *(_DWORD *)(a1 + 8) = 4;
    v13 = 1;
  }
  else
  {
    v13 = 0;
    if ( *(_DWORD *)(a1 + 8) == 1 )
      v13 = 2;
    *(_DWORD *)(a1 + 8) = 2;
    Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
  }
  _Mtx_unlock((_Mtx_t)v8);
  v14 = v13 - 1;
  if ( v14 )
  {
    if ( v14 == 1 )
    {
      v15 = *(_QWORD *)(a1 + 432);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  else
  {
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(a1 + 136));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v18[0] = &std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable';
      v18[1] = a1;
      v19 = v18;
      Concurrency::details::_ScheduleFuncWithAutoInline(v18, 16);
      if ( v19 )
      {
        v16 = v18;
        LOBYTE(v16) = v19 != v18;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v19 + 32LL))(v19, v16);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800586f0  mov     rax, rsp
0x1800586f3  mov     [rax+10h], rbx
0x1800586f7  mov     [rax+18h], rbp
0x1800586fb  push    rsi
0x1800586fc  push    rdi
0x1800586fd  push    r15
0x1800586ff  sub     rsp, 60h
0x180058703  mov     dil, r8b
0x180058706  mov     bpl, dl
0x180058709  mov     rbx, rcx
0x18005870c  lea     rsi, [rcx+20h]
0x180058710  mov     [rax+8], rsi
0x180058714  mov     rcx, rsi; _Mtx_t
0x180058717  call    cs:__imp__Mtx_lock
0x18005871e  nop     dword ptr [rax+rax+00h]
0x180058723  test    eax, eax
0x180058725  jz      short loc_180058739
0x180058727  mov     ecx, 5
0x18005872c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180058733  nop     dword ptr [rax+rax+00h]
0x180058738  int     3; Trap to Debugger
0x180058739  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x180058740  jnz     short loc_18005875B
0x180058742  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x180058749  mov     ecx, 6
0x18005874e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180058755  nop     dword ptr [rax+rax+00h]
0x18005875a  nop
0x18005875b  mov     r15d, 2
0x180058761  mov     eax, [rbx+8]
0x180058764  test    dil, dil
0x180058767  jz      short loc_1800587D8
0x180058769  cmp     eax, 4
0x18005876c  jz      loc_1800588CB
0x180058772  mov     rdx, [rsp+78h+arg_20]
0x18005877a  mov     rax, [rdx+8]
0x18005877e  test    rax, rax
0x180058781  jz      short loc_180058787
0x180058783  lock inc dword ptr [rax+8]
0x180058787  mov     rcx, [rdx+8]
0x18005878b  mov     rax, [rdx]
0x18005878e  mov     [rbx+10h], rax
0x180058792  mov     rdi, [rbx+18h]
0x180058796  mov     [rbx+18h], rcx
0x18005879a  test    rdi, rdi
0x18005879d  jz      short loc_1800587FE
0x18005879f  or      eax, 0FFFFFFFFh
0x1800587a2  lock xadd [rdi+8], eax
0x1800587a7  cmp     eax, 1
0x1800587aa  jnz     short loc_1800587FE
0x1800587ac  mov     rax, [rdi]
0x1800587af  mov     rcx, rdi
0x1800587b2  mov     rax, [rax]
0x1800587b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587ba  or      eax, 0FFFFFFFFh
0x1800587bd  lock xadd [rdi+0Ch], eax
0x1800587c2  cmp     eax, 1
0x1800587c5  jnz     short loc_1800587FE
0x1800587c7  mov     rax, [rdi]
0x1800587ca  mov     rcx, rdi
0x1800587cd  mov     rax, [rax+8]
0x1800587d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587d6  jmp     short loc_1800587FE
0x1800587d8  cmp     eax, 3
0x1800587db  jz      loc_1800588CB
0x1800587e1  mov     eax, [rbx+8]
0x1800587e4  cmp     eax, 4
0x1800587e7  jz      loc_1800588CB
0x1800587ed  mov     eax, [rbx+8]
0x1800587f0  cmp     eax, r15d
0x1800587f3  jnz     short loc_1800587FE
0x1800587f5  test    bpl, bpl
0x1800587f8  jz      loc_1800588CB
0x1800587fe  test    bpl, bpl
0x180058801  jz      short loc_180058811
0x180058803  mov     dword ptr [rbx+8], 4
0x18005880a  mov     edi, 1
0x18005880f  jmp     short loc_180058835
0x180058811  mov     eax, [rbx+8]
0x180058814  xor     edi, edi
0x180058816  cmp     eax, 1
0x180058819  cmovz   edi, r15d
0x18005881d  mov     [rbx+8], r15d
0x180058821  lea     rcx, [rbx+160h]
0x180058828  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x18005882f  nop     dword ptr [rax+rax+00h]
0x180058834  nop
0x180058835  mov     rcx, rsi; _Mtx_t
0x180058838  call    cs:__imp__Mtx_unlock
0x18005883f  nop     dword ptr [rax+rax+00h]
0x180058844  sub     edi, 1
0x180058847  jz      short loc_180058868
0x180058849  cmp     edi, 1
0x18005884c  jnz     short loc_1800588C7
0x18005884e  mov     rcx, [rbx+1B0h]
0x180058855  test    rcx, rcx
0x180058858  jz      short loc_1800588C7
0x18005885a  mov     rax, [rcx]
0x18005885d  mov     rax, [rax+10h]
0x180058861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058866  jmp     short loc_1800588C7
0x180058868  lea     rcx, [rbx+88h]; this
0x18005886f  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x180058874  cmp     qword ptr [rbx+70h], 0
0x180058879  jz      short loc_1800588C7
0x18005887b  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_763529b0c7473cbc215a52d189ac9b18_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_763529b0c7473cbc215a52d189ac9b18_,void,>::`vftable'
0x180058882  mov     [rsp+78h+var_58], rax
0x180058887  mov     [rsp+78h+var_50], rbx
0x18005888c  lea     rax, [rsp+78h+var_58]
0x180058891  mov     [rsp+78h+var_20], rax
0x180058896  mov     edx, 10h
0x18005889b  lea     rcx, [rsp+78h+var_58]
0x1800588a0  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x1800588a5  nop
0x1800588a6  mov     rcx, [rsp+78h+var_20]
0x1800588ab  test    rcx, rcx
0x1800588ae  jz      short loc_1800588C7
0x1800588b0  mov     rax, [rcx]
0x1800588b3  lea     rdx, [rsp+78h+var_58]
0x1800588b8  cmp     rcx, rdx
0x1800588bb  setnz   dl
0x1800588be  mov     rax, [rax+20h]
0x1800588c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588c7  mov     al, 1
0x1800588c9  jmp     short loc_1800588DC
0x1800588cb  mov     rcx, rsi; _Mtx_t
0x1800588ce  call    cs:__imp__Mtx_unlock
0x1800588d5  nop     dword ptr [rax+rax+00h]
0x1800588da  xor     al, al
0x1800588dc  lea     r11, [rsp+78h+var_18]
0x1800588e1  mov     rbx, [r11+28h]
0x1800588e5  mov     rbp, [r11+30h]
0x1800588e9  mov     rsp, r11
0x1800588ec  pop     r15
0x1800588ee  pop     rdi
0x1800588ef  pop     rsi
0x1800588f0  retn
```
