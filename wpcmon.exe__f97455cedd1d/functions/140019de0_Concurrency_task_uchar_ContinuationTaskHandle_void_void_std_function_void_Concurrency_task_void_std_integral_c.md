# Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x140019de0`
- end: `0x14001a02e`
- name: `?_Continue@?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU?$integral_constant@_N$00@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001d630`

## callees

- `0x140005530`
- `0x1400057f0`
- `0x140019de0`
- `0x14001b55c`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140019f72`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140019f72`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140019f49`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140019f49`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140019fd9`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x140019fd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        _QWORD *a1)
{
  __int64 v2; // rax
  _BYTE *v3; // r14
  volatile signed __int32 *v4; // r15
  Concurrency::details::_Task_impl_base *v5; // r12
  _BYTE *v6; // rcx
  char *v7; // rbx
  _BYTE *v8; // rcx
  _BYTE *v9; // rdx
  _BYTE *v10; // rdx
  Concurrency::details::_TaskEventLogger *v11; // rsi
  volatile signed __int32 *v12; // rdi
  __int64 v13; // rdx
  _BYTE *v15; // [rsp+20h] [rbp-E0h] BYREF
  volatile signed __int32 *v16; // [rsp+28h] [rbp-D8h]
  char *v17; // [rsp+30h] [rbp-D0h]
  Concurrency::details::_TaskEventLogger *v18; // [rsp+38h] [rbp-C8h]
  __int128 v19; // [rsp+40h] [rbp-C0h]
  _BYTE v20[56]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v21; // [rsp+88h] [rbp-78h]
  char v22; // [rsp+90h] [rbp-70h] BYREF
  char *v23; // [rsp+C8h] [rbp-38h]
  _BYTE v24[56]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE *v25; // [rsp+108h] [rbp+8h]

  v2 = a1[8];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  v3 = (_BYTE *)a1[7];
  v4 = (volatile signed __int32 *)a1[8];
  *(_QWORD *)&v19 = v3;
  *((_QWORD *)&v19 + 1) = v4;
  v5 = (Concurrency::details::_Task_impl_base *)a1[5];
  v15 = v20;
  v21 = 0;
  v6 = (_BYTE *)a1[16];
  if ( v6 )
  {
    v6 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v6)(v6, v20);
    v21 = v6;
  }
  v15 = v20;
  v17 = v24;
  v25 = 0;
  if ( v6 )
    v25 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v6)(v6, v24);
  v23 = 0;
  v7 = (char *)operator new(0x48u);
  v17 = v7;
  *(_QWORD *)v7 = &std::_Func_impl_no_alloc<_lambda_dfadb08385c0ecb100cd522a7df6a8ea_,unsigned char,Concurrency::task<void>>::`vftable';
  v18 = (Concurrency::details::_TaskEventLogger *)(v7 + 8);
  *((_QWORD *)v7 + 8) = 0;
  v8 = v25;
  if ( v25 )
  {
    *((_QWORD *)v7 + 8) = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v25)(v25, (_QWORD *)v7 + 1);
    v8 = v25;
  }
  v23 = v7;
  if ( v8 )
  {
    v9 = v24;
    LOBYTE(v9) = v8 != v24;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v8 + 32LL))(v8, v9);
  }
  if ( v21 )
  {
    v10 = v20;
    LOBYTE(v10) = v21 != v20;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v21 + 32LL))(v21, v10);
    v21 = 0;
  }
  v11 = (Concurrency::details::_TaskEventLogger *)(a1[5] + 352LL);
  v18 = v11;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v11);
  v15 = v3;
  v16 = v4;
  v19 = 0;
  v17 = (char *)&v15;
  if ( !v7 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(char *, _BYTE **))(*(_QWORD *)v7 + 16LL))(v7, &v15);
  v12 = v16;
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v11);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v5);
  LOBYTE(v13) = v7 != &v22;
  return (*(__int64 (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 32LL))(v7, v13);
}

```

## disassembly

```asm
0x140019de0  mov     [rsp-8+arg_8], rbx
0x140019de5  mov     [rsp-8+arg_10], rsi
0x140019dea  push    rbp
0x140019deb  push    rdi
0x140019dec  push    r12
0x140019dee  push    r14
0x140019df0  push    r15
0x140019df2  lea     rbp, [rsp-20h]
0x140019df7  sub     rsp, 120h
0x140019dfe  mov     rax, cs:__security_cookie
0x140019e05  xor     rax, rsp
0x140019e08  mov     [rbp+40h+var_30], rax
0x140019e0c  mov     rdi, rcx
0x140019e0f  mov     rax, [rcx+40h]
0x140019e13  test    rax, rax
0x140019e16  jz      short loc_140019E1C
0x140019e18  lock inc dword ptr [rax+8]
0x140019e1c  mov     r14, [rcx+38h]
0x140019e20  mov     r15, [rcx+40h]
0x140019e24  mov     qword ptr [rsp+140h+var_100], r14
0x140019e29  mov     qword ptr [rsp+140h+var_100+8], r15
0x140019e2e  mov     r12, [rcx+28h]
0x140019e32  lea     rax, [rsp+140h+var_F0]
0x140019e37  mov     [rsp+140h+var_120], rax
0x140019e3c  mov     [rbp+40h+var_B8], 0
0x140019e44  mov     rcx, [rcx+80h]
0x140019e4b  test    rcx, rcx
0x140019e4e  jz      short loc_140019E67
0x140019e50  mov     rax, [rcx]
0x140019e53  lea     rdx, [rsp+140h+var_F0]
0x140019e58  mov     rax, [rax]
0x140019e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e60  mov     rcx, rax
0x140019e63  mov     [rbp+40h+var_B8], rax
0x140019e67  lea     rax, [rsp+140h+var_F0]
0x140019e6c  mov     [rsp+140h+var_120], rax
0x140019e71  lea     rax, [rbp+40h+var_70]
0x140019e75  mov     [rsp+140h+var_110], rax
0x140019e7a  mov     [rbp+40h+var_38], 0
0x140019e82  test    rcx, rcx
0x140019e85  jz      short loc_140019E9A
0x140019e87  mov     rax, [rcx]
0x140019e8a  lea     rdx, [rbp+40h+var_70]
0x140019e8e  mov     rax, [rax]
0x140019e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e96  mov     [rbp+40h+var_38], rax
0x140019e9a  mov     [rbp+40h+var_78], 0
0x140019ea2  mov     ecx, 48h ; 'H'; Size
0x140019ea7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140019eac  mov     rbx, rax
0x140019eaf  mov     [rsp+140h+var_110], rax
0x140019eb4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_dfadb08385c0ecb100cd522a7df6a8ea_@@EV?$task@X@Concurrency@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_dfadb08385c0ecb100cd522a7df6a8ea_,uchar,Concurrency::task<void>>::`vftable'
0x140019ebb  mov     [rbx], rax
0x140019ebe  lea     rsi, [rbx+8]
0x140019ec2  mov     [rsp+140h+var_108], rsi
0x140019ec7  mov     qword ptr [rsi+38h], 0
0x140019ecf  mov     rcx, [rbp+40h+var_38]
0x140019ed3  test    rcx, rcx
0x140019ed6  jz      short loc_140019EEE
0x140019ed8  mov     rax, [rcx]
0x140019edb  mov     rdx, rsi
0x140019ede  mov     rax, [rax]
0x140019ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019ee6  mov     [rsi+38h], rax
0x140019eea  mov     rcx, [rbp+40h+var_38]
0x140019eee  mov     [rbp+40h+var_78], rbx
0x140019ef2  test    rcx, rcx
0x140019ef5  jz      short loc_140019F0E
0x140019ef7  mov     rax, [rcx]
0x140019efa  lea     rdx, [rbp+40h+var_70]
0x140019efe  cmp     rcx, rdx
0x140019f01  setnz   dl
0x140019f04  mov     rax, [rax+20h]
0x140019f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f0d  nop
0x140019f0e  mov     rcx, [rbp+40h+var_B8]
0x140019f12  test    rcx, rcx
0x140019f15  jz      short loc_140019F36
0x140019f17  mov     rax, [rcx]
0x140019f1a  lea     rdx, [rsp+140h+var_F0]
0x140019f1f  cmp     rcx, rdx
0x140019f22  setnz   dl
0x140019f25  mov     rax, [rax+20h]
0x140019f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f2e  mov     [rbp+40h+var_B8], 0
0x140019f36  mov     rsi, [rdi+28h]
0x140019f3a  add     rsi, 160h
0x140019f41  mov     [rsp+140h+var_108], rsi
0x140019f46  mov     rcx, rsi
0x140019f49  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x140019f4f  nop
0x140019f50  mov     [rsp+140h+var_120], r14
0x140019f55  mov     [rsp+140h+var_118], r15
0x140019f5a  xorps   xmm0, xmm0
0x140019f5d  movdqu  [rsp+140h+var_100], xmm0
0x140019f63  lea     rax, [rsp+140h+var_120]
0x140019f68  mov     [rsp+140h+var_110], rax
0x140019f6d  test    rbx, rbx
0x140019f70  jnz     short loc_140019F79
0x140019f72  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x140019f78  int     3; Trap to Debugger
0x140019f79  mov     rax, [rbx]
0x140019f7c  lea     rdx, [rsp+140h+var_120]
0x140019f81  mov     rcx, rbx
0x140019f84  mov     rax, [rax+10h]
0x140019f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019f8d  mov     r14b, al
0x140019f90  mov     rdi, [rsp+140h+var_118]
0x140019f95  test    rdi, rdi
0x140019f98  jz      short loc_140019FD6
0x140019f9a  or      r15d, 0FFFFFFFFh
0x140019f9e  mov     ecx, r15d
0x140019fa1  lock xadd [rdi+8], ecx
0x140019fa6  add     ecx, r15d
0x140019fa9  jnz     short loc_140019FD6
0x140019fab  mov     rdx, [rdi]
0x140019fae  mov     rcx, rdi
0x140019fb1  mov     rax, [rdx]
0x140019fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019fb9  mov     eax, r15d
0x140019fbc  lock xadd [rdi+0Ch], eax
0x140019fc1  add     eax, r15d
0x140019fc4  jnz     short loc_140019FD6
0x140019fc6  mov     rax, [rdi]
0x140019fc9  mov     rcx, rdi
0x140019fcc  mov     rax, [rax+8]
0x140019fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019fd5  nop
0x140019fd6  mov     rcx, rsi
0x140019fd9  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x140019fdf  nop
0x140019fe0  mov     dl, r14b
0x140019fe3  mov     rcx, r12; this
0x140019fe6  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x140019feb  nop
0x140019fec  mov     rax, [rbx]
0x140019fef  lea     rcx, [rbp+40h+var_B0]
0x140019ff3  cmp     rbx, rcx
0x140019ff6  setnz   dl
0x140019ff9  mov     rcx, rbx
0x140019ffc  mov     rax, [rax+20h]
0x14001a000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a005  nop
0x14001a006  mov     rcx, [rbp+40h+var_30]
0x14001a00a  xor     rcx, rsp; StackCookie
0x14001a00d  call    __security_check_cookie
0x14001a012  lea     r11, [rsp+140h+var_20]
0x14001a01a  mov     rbx, [r11+38h]
0x14001a01e  mov     rsi, [r11+40h]
0x14001a022  mov     rsp, r11
0x14001a025  pop     r15
0x14001a027  pop     r14
0x14001a029  pop     r12
0x14001a02b  pop     rdi
0x14001a02c  pop     rbp
0x14001a02d  retn
```
