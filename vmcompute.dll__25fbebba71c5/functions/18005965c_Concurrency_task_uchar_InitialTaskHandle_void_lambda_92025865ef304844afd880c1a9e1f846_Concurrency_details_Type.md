# Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18005965c`
- end: `0x18005989d`
- name: `?_Init@?$_InitialTaskHandle@XV_lambda_92025865ef304844afd880c1a9e1f846_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005a5f0`

## callees

- `0x180002f74`
- `0x180058b68`
- `0x180058cd0`
- `0x18005965c`
- `0x180059cfc`
- `0x180086010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005978a`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005978a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800597bf`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800597bf`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800597a0`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800597a0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059816`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059837`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059816`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180059837`
- `msvcp_win!_Mtx_lock` at `0x180059801`
- `msvcp_win!_Mtx_lock` at `0x180059801`
- `msvcp_win!_Mtx_unlock` at `0x18005984f`
- `msvcp_win!_Mtx_unlock` at `0x180059864`
- `msvcp_win!_Mtx_unlock` at `0x18005984f`
- `msvcp_win!_Mtx_unlock` at `0x180059864`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>::_Init(
        __int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx
  _BYTE *v4; // rcx
  _BYTE *v5; // rdx
  _QWORD *v6; // rdx
  Concurrency::details::_TaskEventLogger *v7; // rbx
  _BYTE *v8; // rcx
  char v9; // si
  _BYTE *v10; // rdx
  struct _Mtx_internal_imp_t *v11; // rcx
  _QWORD v12[7]; // [rsp+40h] [rbp-79h] BYREF
  _QWORD *v13; // [rsp+78h] [rbp-41h]
  _BYTE v14[56]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE *v15; // [rsp+B8h] [rbp-1h]
  _BYTE v16[56]; // [rsp+C0h] [rbp+7h] BYREF
  _BYTE *v17; // [rsp+F8h] [rbp+3Fh]

  v2 = *(_QWORD *)(a1 + 8);
  v12[0] = &std::_Func_impl_no_alloc<_lambda_92025865ef304844afd880c1a9e1f846_,void,>::`vftable';
  v12[1] = *(_QWORD *)(a1 + 24);
  v13 = v12;
  v15 = 0;
  v15 = (_BYTE *)std::_Func_impl_no_alloc<_lambda_92025865ef304844afd880c1a9e1f846_,void,>::_Copy(v12, v14);
  v17 = 0;
  v3 = operator new(0x48u);
  *v3 = &std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::`vftable';
  v3[8] = 0;
  v4 = v15;
  if ( v15 )
  {
    v3[8] = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v15)(v15, v3 + 1);
    v4 = v15;
  }
  v17 = v3;
  if ( v4 )
  {
    v5 = v14;
    LOBYTE(v5) = v4 != v14;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v4 + 32LL))(v4, v5);
    v15 = 0;
  }
  if ( v13 )
  {
    v6 = v12;
    LOBYTE(v6) = v13 != v12;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v13 + 32LL))(v13, v6);
    v13 = 0;
  }
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v8 = v17;
  if ( !v17 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v9 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v8 + 16LL))(v8);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  if ( v17 )
  {
    v10 = v16;
    LOBYTE(v10) = v17 != v16;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v17 + 32LL))(v17, v10);
    v17 = 0;
  }
  *(_BYTE *)(v2 + 368) = v9;
  if ( _Mtx_lock((_Mtx_t)(v2 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v2 + 108) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 108) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v11 = (struct _Mtx_internal_imp_t *)(v2 + 32);
  if ( *(_DWORD *)(v2 + 8) == 4 )
  {
    _Mtx_unlock(v11);
  }
  else
  {
    *(_DWORD *)(v2 + 8) = 3;
    _Mtx_unlock(v11);
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(v2 + 136));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
}

```

## disassembly

```asm
0x18005965c  mov     [rsp-8+arg_8], rbx
0x180059661  mov     [rsp-8+arg_10], rsi
0x180059666  push    rbp
0x180059667  push    rdi
0x180059668  push    r14
0x18005966a  lea     rbp, [rsp-47h]
0x18005966f  sub     rsp, 100h
0x180059676  mov     r14, rcx
0x180059679  mov     rdi, [rcx+8]
0x18005967d  lea     rax, [rbp+57h+var_50]
0x180059681  mov     [rsp+110h+var_E8], rax
0x180059686  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_92025865ef304844afd880c1a9e1f846_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_92025865ef304844afd880c1a9e1f846_,void,>::`vftable'
0x18005968d  mov     [rbp+57h+var_D0], rax
0x180059691  mov     rax, [rcx+18h]
0x180059695  mov     [rbp+57h+var_C8], rax
0x180059699  lea     rax, [rbp+57h+var_D0]
0x18005969d  mov     [rbp+57h+var_98], rax
0x1800596a1  lea     rax, [rbp+57h+var_D0]
0x1800596a5  mov     [rsp+110h+var_E0], rax
0x1800596aa  lea     rax, [rbp+57h+var_90]
0x1800596ae  mov     [rsp+110h+var_F0], rax
0x1800596b3  mov     [rbp+57h+var_58], 0
0x1800596bb  lea     rdx, [rbp+57h+var_90]
0x1800596bf  lea     rcx, [rbp+57h+var_D0]
0x1800596c3  call    ?_Copy@?$_Func_impl_no_alloc@V_lambda_92025865ef304844afd880c1a9e1f846_@@X$$V@std@@EEBAPEAV?$_Func_base@X$$V@2@PEAX@Z; std::_Func_impl_no_alloc<_lambda_92025865ef304844afd880c1a9e1f846_,void,>::_Copy(void *)
0x1800596c8  mov     [rbp+57h+var_58], rax
0x1800596cc  mov     [rbp+57h+var_18], 0
0x1800596d4  mov     ecx, 48h ; 'H'; Size
0x1800596d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800596de  mov     rbx, rax
0x1800596e1  mov     [rsp+110h+var_F0], rax
0x1800596e6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::`vftable'
0x1800596ed  mov     [rbx], rax
0x1800596f0  lea     rsi, [rbx+8]
0x1800596f4  mov     [rsp+110h+var_D8], rsi
0x1800596f9  mov     qword ptr [rsi+38h], 0
0x180059701  mov     rcx, [rbp+57h+var_58]
0x180059705  test    rcx, rcx
0x180059708  jz      short loc_180059720
0x18005970a  mov     rax, [rcx]
0x18005970d  mov     rdx, rsi
0x180059710  mov     rax, [rax]
0x180059713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059718  mov     [rsi+38h], rax
0x18005971c  mov     rcx, [rbp+57h+var_58]
0x180059720  mov     [rbp+57h+var_18], rbx
0x180059724  test    rcx, rcx
0x180059727  jz      short loc_180059747
0x180059729  mov     rax, [rcx]
0x18005972c  lea     rdx, [rbp+57h+var_90]
0x180059730  cmp     rcx, rdx
0x180059733  setnz   dl
0x180059736  mov     rax, [rax+20h]
0x18005973a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005973f  mov     [rbp+57h+var_58], 0
0x180059747  mov     rcx, [rbp+57h+var_98]
0x18005974b  test    rcx, rcx
0x18005974e  jz      short loc_18005976E
0x180059750  mov     rax, [rcx]
0x180059753  lea     rdx, [rbp+57h+var_D0]
0x180059757  cmp     rcx, rdx
0x18005975a  setnz   dl
0x18005975d  mov     rax, [rax+20h]
0x180059761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059766  mov     [rbp+57h+var_98], 0
0x18005976e  lea     rax, [rbp+57h+var_50]
0x180059772  mov     [rsp+110h+var_D8], rax
0x180059777  mov     rbx, [r14+8]
0x18005977b  add     rbx, 160h
0x180059782  mov     [rsp+110h+var_F0], rbx
0x180059787  mov     rcx, rbx
0x18005978a  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180059791  nop     dword ptr [rax+rax+00h]
0x180059796  nop
0x180059797  mov     rcx, [rbp+57h+var_18]
0x18005979b  test    rcx, rcx
0x18005979e  jnz     short loc_1800597AD
0x1800597a0  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800597a7  nop     dword ptr [rax+rax+00h]
0x1800597ac  int     3; Trap to Debugger
0x1800597ad  mov     rax, [rcx]
0x1800597b0  mov     rax, [rax+10h]
0x1800597b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597b9  mov     sil, al
0x1800597bc  mov     rcx, rbx
0x1800597bf  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1800597c6  nop     dword ptr [rax+rax+00h]
0x1800597cb  nop
0x1800597cc  mov     rcx, [rbp+57h+var_18]
0x1800597d0  test    rcx, rcx
0x1800597d3  jz      short loc_1800597F3
0x1800597d5  mov     rdx, [rcx]
0x1800597d8  mov     rax, [rdx+20h]
0x1800597dc  lea     rdx, [rbp+57h+var_50]
0x1800597e0  cmp     rcx, rdx
0x1800597e3  setnz   dl
0x1800597e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597eb  mov     [rbp+57h+var_18], 0
0x1800597f3  mov     [rdi+170h], sil
0x1800597fa  lea     rbx, [rdi+20h]
0x1800597fe  mov     rcx, rbx; _Mtx_t
0x180059801  call    cs:__imp__Mtx_lock
0x180059808  nop     dword ptr [rax+rax+00h]
0x18005980d  test    eax, eax
0x18005980f  jz      short loc_180059823
0x180059811  mov     ecx, 5
0x180059816  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005981d  nop     dword ptr [rax+rax+00h]
0x180059822  int     3; Trap to Debugger
0x180059823  mov     eax, [rbx+4Ch]
0x180059826  cmp     eax, 7FFFFFFFh
0x18005982b  jnz     short loc_180059844
0x18005982d  dec     eax
0x18005982f  mov     [rbx+4Ch], eax
0x180059832  mov     ecx, 6
0x180059837  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005983e  nop     dword ptr [rax+rax+00h]
0x180059843  int     3; Trap to Debugger
0x180059844  mov     eax, [rdi+8]
0x180059847  mov     rcx, rbx; _Mtx_t
0x18005984a  cmp     eax, 4
0x18005984d  jnz     short loc_18005985D
0x18005984f  call    cs:__imp__Mtx_unlock
0x180059856  nop     dword ptr [rax+rax+00h]
0x18005985b  jmp     short loc_180059884
0x18005985d  mov     dword ptr [rdi+8], 3
0x180059864  call    cs:__imp__Mtx_unlock
0x18005986b  nop     dword ptr [rax+rax+00h]
0x180059870  lea     rcx, [rdi+88h]; this
0x180059877  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x18005987c  mov     rcx, rdi; this
0x18005987f  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x180059884  lea     r11, [rsp+110h+var_10]
0x18005988c  mov     rbx, [r11+28h]
0x180059890  mov     rsi, [r11+30h]
0x180059894  mov     rsp, r11
0x180059897  pop     r14
0x180059899  pop     rdi
0x18005989a  pop     rbp
0x18005989b  retn
```
