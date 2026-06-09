# Concurrency::details::_Task_impl<Optional<bool>>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x14004ba00`
- end: `0x14004bba2`
- name: `?_CancelAndRunContinuations@?$_Task_impl@V?$Optional@_N@@@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005530`
- `0x14000e298`
- `0x140019d60`
- `0x14001beb4`
- `0x14004ba00`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x14004baed`
- `msvcp_win!_Mtx_unlock` at `0x14004bb7d`
- `msvcp_win!_Mtx_unlock` at `0x14004baed`
- `msvcp_win!_Mtx_unlock` at `0x14004bb7d`
- `msvcp_win!_Mtx_lock` at `0x14004ba3c`
- `msvcp_win!_Mtx_lock` at `0x14004ba3c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14004ba4b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14004ba67`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14004ba4b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14004ba67`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14004bae3`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14004bae3`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<Optional<bool>>::_CancelAndRunContinuations(
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
      v12 = *(_QWORD *)(a1 + 440);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  else
  {
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(a1 + 136));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v15[0] = &std::_Func_impl_no_alloc<_lambda_685c63b67b8695329c451d7510d80b4d_,void,>::`vftable';
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
0x14004ba00  push    rbx
0x14004ba02  push    rbp
0x14004ba03  push    rsi
0x14004ba04  push    rdi
0x14004ba05  push    r14
0x14004ba07  push    r15
0x14004ba09  sub     rsp, 88h
0x14004ba10  mov     rax, cs:__security_cookie
0x14004ba17  xor     rax, rsp
0x14004ba1a  mov     [rsp+0B8h+var_48], rax
0x14004ba1f  mov     bpl, r8b
0x14004ba22  mov     dil, dl
0x14004ba25  mov     rbx, rcx
0x14004ba28  mov     r14, [rsp+0B8h+arg_20]
0x14004ba30  lea     rsi, [rcx+20h]
0x14004ba34  mov     [rsp+0B8h+var_98], rsi
0x14004ba39  mov     rcx, rsi; _Mtx_t
0x14004ba3c  call    cs:__imp__Mtx_lock
0x14004ba42  test    eax, eax
0x14004ba44  jz      short loc_14004BA52
0x14004ba46  mov     ecx, 5
0x14004ba4b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14004ba51  int     3; Trap to Debugger
0x14004ba52  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x14004ba59  jnz     short loc_14004BA6E
0x14004ba5b  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x14004ba62  mov     ecx, 6
0x14004ba67  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14004ba6d  nop
0x14004ba6e  mov     r15d, 2
0x14004ba74  mov     eax, [rbx+8]
0x14004ba77  test    bpl, bpl
0x14004ba7a  jz      short loc_14004BA93
0x14004ba7c  cmp     eax, 4
0x14004ba7f  jz      loc_14004BB7A
0x14004ba85  lea     rcx, [rbx+10h]
0x14004ba89  mov     rdx, r14
0x14004ba8c  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x14004ba91  jmp     short loc_14004BAB9
0x14004ba93  cmp     eax, 3
0x14004ba96  jz      loc_14004BB7A
0x14004ba9c  mov     eax, [rbx+8]
0x14004ba9f  cmp     eax, 4
0x14004baa2  jz      loc_14004BB7A
0x14004baa8  mov     eax, [rbx+8]
0x14004baab  cmp     eax, r15d
0x14004baae  jnz     short loc_14004BAB9
0x14004bab0  test    dil, dil
0x14004bab3  jz      loc_14004BB7A
0x14004bab9  test    dil, dil
0x14004babc  jz      short loc_14004BACC
0x14004babe  mov     dword ptr [rbx+8], 4
0x14004bac5  mov     edi, 1
0x14004baca  jmp     short loc_14004BAEA
0x14004bacc  mov     eax, [rbx+8]
0x14004bacf  xor     edi, edi
0x14004bad1  cmp     eax, 1
0x14004bad4  cmovz   edi, r15d
0x14004bad8  mov     [rbx+8], r15d
0x14004badc  lea     rcx, [rbx+160h]
0x14004bae3  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x14004bae9  nop
0x14004baea  mov     rcx, rsi; _Mtx_t
0x14004baed  call    cs:__imp__Mtx_unlock
0x14004baf3  sub     edi, 1
0x14004baf6  jz      short loc_14004BB17
0x14004baf8  cmp     edi, 1
0x14004bafb  jnz     short loc_14004BB76
0x14004bafd  mov     rcx, [rbx+1B8h]
0x14004bb04  test    rcx, rcx
0x14004bb07  jz      short loc_14004BB76
0x14004bb09  mov     rax, [rcx]
0x14004bb0c  mov     rax, [rax+10h]
0x14004bb10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bb15  jmp     short loc_14004BB76
0x14004bb17  lea     rcx, [rbx+88h]; this
0x14004bb1e  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x14004bb23  cmp     qword ptr [rbx+70h], 0
0x14004bb28  jz      short loc_14004BB76
0x14004bb2a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_685c63b67b8695329c451d7510d80b4d_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_685c63b67b8695329c451d7510d80b4d_,void,>::`vftable'
0x14004bb31  mov     [rsp+0B8h+var_88], rax
0x14004bb36  mov     [rsp+0B8h+var_80], rbx
0x14004bb3b  lea     rax, [rsp+0B8h+var_88]
0x14004bb40  mov     [rsp+0B8h+var_50], rax
0x14004bb45  mov     edx, 10h
0x14004bb4a  lea     rcx, [rsp+0B8h+var_88]
0x14004bb4f  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x14004bb54  nop
0x14004bb55  mov     rcx, [rsp+0B8h+var_50]
0x14004bb5a  test    rcx, rcx
0x14004bb5d  jz      short loc_14004BB76
0x14004bb5f  mov     rax, [rcx]
0x14004bb62  lea     rdx, [rsp+0B8h+var_88]
0x14004bb67  cmp     rcx, rdx
0x14004bb6a  setnz   dl
0x14004bb6d  mov     rax, [rax+20h]
0x14004bb71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004bb76  mov     al, 1
0x14004bb78  jmp     short loc_14004BB85
0x14004bb7a  mov     rcx, rsi; _Mtx_t
0x14004bb7d  call    cs:__imp__Mtx_unlock
0x14004bb83  xor     al, al
0x14004bb85  mov     rcx, [rsp+0B8h+var_48]
0x14004bb8a  xor     rcx, rsp; StackCookie
0x14004bb8d  call    __security_check_cookie
0x14004bb92  add     rsp, 88h
0x14004bb99  pop     r15
0x14004bb9b  pop     r14
0x14004bb9d  pop     rdi
0x14004bb9e  pop     rsi
0x14004bb9f  pop     rbp
0x14004bba0  pop     rbx
0x14004bba1  retn
```
