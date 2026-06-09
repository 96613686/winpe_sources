# Concurrency::task_completion_event<DockedClient::AppInstallResult>::_Cancel<std::exception_ptr>(std::exception_ptr,Concurrency::details::_TaskCreationCallstack const &)

- ea: `0x180027460`
- end: `0x180027654`
- name: `??$_Cancel@Vexception_ptr@std@@@?$task_completion_event@UAppInstallResult@DockedClient@@@Concurrency@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003bb8c`

## callees

- `0x180007660`
- `0x180007dfc`
- `0x180027460`
- `0x18002a24c`
- `0x1800382a4`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800275f8`
- `msvcp_win!_Mtx_unlock` at `0x180027618`
- `msvcp_win!_Mtx_unlock` at `0x1800275f8`
- `msvcp_win!_Mtx_unlock` at `0x180027618`
- `msvcp_win!_Mtx_lock` at `0x1800274b8`
- `msvcp_win!_Mtx_lock` at `0x1800274b8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800274c7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800274e2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800274c7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800274e2`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002759b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180027603`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180027623`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002762e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002759b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180027603`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180027623`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002762e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002749c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180027524`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180027583`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002749c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180027524`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180027583`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Concurrency::task_completion_event<DockedClient::AppInstallResult>::_Cancel<std::exception_ptr>(
        __int64 *a1,
        void *a2,
        const struct Concurrency::details::_TaskCreationCallstack *a3)
{
  __int64 v6; // rsi
  __int64 v7; // rax
  _DWORD *v8; // rdi
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  char v11; // bl
  __int128 v13; // [rsp+20h] [rbp-60h] BYREF
  __int128 *v14; // [rsp+30h] [rbp-50h]
  __int128 v15; // [rsp+38h] [rbp-48h] BYREF
  __int128 *v16; // [rsp+48h] [rbp-38h]
  __int64 v17; // [rsp+50h] [rbp-30h]
  _DWORD *v18; // [rsp+58h] [rbp-28h]
  char *v19; // [rsp+60h] [rbp-20h]
  void *v20; // [rsp+68h] [rbp-18h]

  v20 = a2;
  v13 = 0;
  __ExceptionPtrCopy(&v13, a2);
  v14 = &v13;
  v6 = *a1 + 24;
  v17 = v6;
  if ( _Mtx_lock((_Mtx_t)v6) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v6 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v6 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v7 = *a1;
  if ( *(_BYTE *)(*a1 + 144) || *(_BYTE *)(v7 + 145) || *(_QWORD *)(v7 + 128) )
  {
    _Mtx_unlock((_Mtx_t)v6);
    __ExceptionPtrDestroy(&v13);
    v11 = 0;
  }
  else
  {
    v15 = 0;
    __ExceptionPtrCopy(&v15, &v13);
    v16 = &v15;
    v8 = operator new(0x48u);
    v18 = v8;
    *(_OWORD *)v8 = 0;
    v8[2] = 1;
    v8[3] = 1;
    *(_QWORD *)v8 = &std::_Ref_count_obj2<Concurrency::details::_ExceptionHolder>::`vftable';
    v19 = (char *)(v8 + 4);
    v8[4] = 0;
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 4) = 0;
    __ExceptionPtrCopy(v8 + 6, &v15);
    Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
      (Concurrency::details::_TaskCreationCallstack *)(v8 + 10),
      a3);
    __ExceptionPtrDestroy(&v15);
    v9 = *a1;
    *(_QWORD *)(v9 + 128) = v8 + 4;
    v10 = *(volatile signed __int32 **)(v9 + 136);
    *(_QWORD *)(v9 + 136) = v8;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    _Mtx_unlock((_Mtx_t)v6);
    __ExceptionPtrDestroy(&v13);
    v11 = Concurrency::task_completion_event<DockedClient::AppInstallResult>::_CancelInternal(a1);
  }
  __ExceptionPtrDestroy(a2);
  return v11;
}

```

## disassembly

```asm
0x180027460  push    rbp
0x180027462  push    rbx
0x180027463  push    rsi
0x180027464  push    rdi
0x180027465  push    r12
0x180027467  push    r14
0x180027469  push    r15
0x18002746b  mov     rbp, rsp
0x18002746e  sub     rsp, 80h
0x180027475  mov     rax, cs:__security_cookie
0x18002747c  xor     rax, rsp
0x18002747f  mov     [rbp+var_10], rax
0x180027483  mov     r12, r8
0x180027486  mov     r15, rdx
0x180027489  mov     r14, rcx
0x18002748c  mov     [rbp+var_18], rdx
0x180027490  xorps   xmm0, xmm0
0x180027493  movdqu  [rbp+var_60], xmm0
0x180027498  lea     rcx, [rbp+var_60]
0x18002749c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800274a2  lea     rax, [rbp+var_60]
0x1800274a6  mov     [rbp+var_50], rax
0x1800274aa  mov     rsi, [r14]
0x1800274ad  add     rsi, 18h
0x1800274b1  mov     [rbp+var_30], rsi
0x1800274b5  mov     rcx, rsi; _Mtx_t
0x1800274b8  call    cs:__imp__Mtx_lock
0x1800274be  test    eax, eax
0x1800274c0  jz      short loc_1800274CE
0x1800274c2  mov     ecx, 5
0x1800274c7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800274cd  int     3; Trap to Debugger
0x1800274ce  mov     eax, [rsi+4Ch]
0x1800274d1  cmp     eax, 7FFFFFFFh
0x1800274d6  jnz     short loc_1800274E9
0x1800274d8  dec     eax
0x1800274da  mov     [rsi+4Ch], eax
0x1800274dd  mov     ecx, 6
0x1800274e2  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800274e8  nop
0x1800274e9  mov     rax, [r14]
0x1800274ec  cmp     byte ptr [rax+90h], 0
0x1800274f3  jnz     loc_180027615
0x1800274f9  cmp     byte ptr [rax+91h], 0
0x180027500  jnz     loc_180027615
0x180027506  cmp     qword ptr [rax+80h], 0
0x18002750e  jnz     loc_180027615
0x180027514  xorps   xmm0, xmm0
0x180027517  movdqu  [rbp+var_48], xmm0
0x18002751c  lea     rdx, [rbp+var_60]
0x180027520  lea     rcx, [rbp+var_48]
0x180027524  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002752a  lea     rax, [rbp+var_48]
0x18002752e  mov     [rbp+var_38], rax
0x180027532  mov     ecx, 48h ; 'H'; Size
0x180027537  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002753c  mov     rdi, rax
0x18002753f  mov     [rbp+var_28], rax
0x180027543  xorps   xmm0, xmm0
0x180027546  movups  xmmword ptr [rax], xmm0
0x180027549  mov     eax, 1
0x18002754e  mov     [rdi+8], eax
0x180027551  mov     [rdi+0Ch], eax
0x180027554  lea     rax, ??_7?$_Ref_count_obj2@U_ExceptionHolder@details@Concurrency@@@std@@6B@; const std::_Ref_count_obj2<Concurrency::details::_ExceptionHolder>::`vftable'
0x18002755b  mov     [rdi], rax
0x18002755e  lea     rbx, [rdi+10h]
0x180027562  mov     [rbp+var_20], rbx
0x180027566  mov     dword ptr [rbx], 0
0x18002756c  lea     rcx, [rbx+8]
0x180027570  mov     qword ptr [rcx], 0
0x180027577  mov     qword ptr [rcx+8], 0
0x18002757f  lea     rdx, [rbp+var_48]
0x180027583  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180027589  nop
0x18002758a  lea     rcx, [rbx+18h]; this
0x18002758e  mov     rdx, r12; struct Concurrency::details::_TaskCreationCallstack *
0x180027591  call    ??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z; Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)
0x180027596  nop
0x180027597  lea     rcx, [rbp+var_48]
0x18002759b  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800275a1  mov     rax, [r14]
0x1800275a4  mov     [rax+80h], rbx
0x1800275ab  mov     rbx, [rax+88h]
0x1800275b2  mov     [rax+88h], rdi
0x1800275b9  test    rbx, rbx
0x1800275bc  jz      short loc_1800275F5
0x1800275be  or      edi, 0FFFFFFFFh
0x1800275c1  mov     eax, edi
0x1800275c3  lock xadd [rbx+8], eax
0x1800275c8  add     eax, edi
0x1800275ca  jnz     short loc_1800275F5
0x1800275cc  mov     rax, [rbx]
0x1800275cf  mov     rcx, rbx
0x1800275d2  mov     rax, [rax]
0x1800275d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275da  mov     eax, edi
0x1800275dc  lock xadd [rbx+0Ch], eax
0x1800275e1  add     eax, edi
0x1800275e3  jnz     short loc_1800275F5
0x1800275e5  mov     rax, [rbx]
0x1800275e8  mov     rcx, rbx
0x1800275eb  mov     rax, [rax+8]
0x1800275ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275f4  nop
0x1800275f5  mov     rcx, rsi; _Mtx_t
0x1800275f8  call    cs:__imp__Mtx_unlock
0x1800275fe  nop
0x1800275ff  lea     rcx, [rbp+var_60]
0x180027603  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180027609  mov     rcx, r14
0x18002760c  call    ?_CancelInternal@?$task_completion_event@UAppInstallResult@DockedClient@@@Concurrency@@AEBA_NXZ; Concurrency::task_completion_event<DockedClient::AppInstallResult>::_CancelInternal(void)
0x180027611  mov     bl, al
0x180027613  jmp     short loc_18002762B
0x180027615  mov     rcx, rsi; _Mtx_t
0x180027618  call    cs:__imp__Mtx_unlock
0x18002761e  nop
0x18002761f  lea     rcx, [rbp+var_60]
0x180027623  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180027629  xor     bl, bl
0x18002762b  mov     rcx, r15
0x18002762e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180027634  mov     al, bl
0x180027636  mov     rcx, [rbp+var_10]
0x18002763a  xor     rcx, rsp; StackCookie
0x18002763d  call    __security_check_cookie
0x180027642  add     rsp, 80h
0x180027649  pop     r15
0x18002764b  pop     r14
0x18002764d  pop     r12
0x18002764f  pop     rdi
0x180027650  pop     rsi
0x180027651  pop     rbx
0x180027652  pop     rbp
0x180027653  retn
```
