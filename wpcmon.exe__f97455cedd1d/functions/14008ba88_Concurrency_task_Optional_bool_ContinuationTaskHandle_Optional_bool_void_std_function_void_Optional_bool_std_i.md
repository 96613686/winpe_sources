# Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x14008ba88`
- end: `0x14008bcbc`
- name: `?_Continue@?$_ContinuationTaskHandle@V?$Optional@_N@@XV?$function@$$A6AXV?$Optional@_N@@@Z@std@@U?$integral_constant@_N$0A@@3@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$Optional@_N@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14008c1b0`

## callees

- `0x140005530`
- `0x1400057f0`
- `0x14001b55c`
- `0x14008ba88`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14008bc39`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x14008bc39`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008bbf9`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008bbf9`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008bc6b`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x14008bc6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Concurrency::task<Optional<bool>>::_ContinuationTaskHandle<Optional<bool>,void,std::function<void (Optional<bool>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        _QWORD *a1)
{
  Concurrency::details::_Task_impl_base *v2; // r14
  char *v3; // rax
  _BYTE *v4; // rcx
  char *v5; // rbx
  _BYTE *v6; // rcx
  _BYTE *v7; // rdx
  _BYTE *v8; // rdx
  Concurrency::details::_TaskEventLogger *v9; // rdi
  __int64 v10; // rdx
  _BYTE *v12; // [rsp+20h] [rbp-E0h] BYREF
  char *v13; // [rsp+28h] [rbp-D8h]
  char *v14; // [rsp+30h] [rbp-D0h]
  Concurrency::details::_TaskEventLogger *v15; // [rsp+38h] [rbp-C8h]
  _BYTE v16[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v17; // [rsp+78h] [rbp-88h]
  char v18; // [rsp+80h] [rbp-80h] BYREF
  char *v19; // [rsp+B8h] [rbp-48h]
  char v20; // [rsp+C1h] [rbp-3Fh] BYREF
  char *v21; // [rsp+C8h] [rbp-38h]
  _BYTE v22[56]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE *v23; // [rsp+108h] [rbp+8h]

  v2 = (Concurrency::details::_Task_impl_base *)a1[5];
  v3 = *(char **)(a1[7] + 376LL);
  if ( v3 )
  {
    v20 = *v3;
    v21 = &v20;
  }
  else
  {
    v21 = 0;
  }
  v12 = v16;
  v17 = 0;
  v4 = (_BYTE *)a1[16];
  if ( v4 )
  {
    v4 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v4)(v4, v16);
    v17 = v4;
  }
  v12 = v16;
  v14 = v22;
  v23 = 0;
  if ( v4 )
    v23 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v4)(v4, v22);
  v19 = 0;
  v5 = (char *)operator new(0x48u);
  v14 = v5;
  *(_QWORD *)v5 = &std::_Func_impl_no_alloc<_lambda_96918ec15c0d1e6d6bb3c1d07c4f36b8_,unsigned char,Optional<bool>>::`vftable';
  v15 = (Concurrency::details::_TaskEventLogger *)(v5 + 8);
  *((_QWORD *)v5 + 8) = 0;
  v6 = v23;
  if ( v23 )
  {
    *((_QWORD *)v5 + 8) = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v23)(v23, (_QWORD *)v5 + 1);
    v6 = v23;
  }
  v19 = v5;
  if ( v6 )
  {
    v7 = v22;
    LOBYTE(v7) = v6 != v22;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v6 + 32LL))(v6, v7);
  }
  if ( v17 )
  {
    v8 = v16;
    LOBYTE(v8) = v17 != v16;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v17 + 32LL))(v17, v8);
    v17 = 0;
  }
  v9 = (Concurrency::details::_TaskEventLogger *)(a1[5] + 352LL);
  v15 = v9;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v9);
  v13 = 0;
  if ( v21 )
  {
    BYTE1(v12) = *v21;
    v13 = (char *)&v12 + 1;
    v21 = 0;
  }
  v14 = (char *)&v12;
  if ( !v5 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(char *, _BYTE **))(*(_QWORD *)v5 + 16LL))(v5, &v12);
  if ( v13 )
    v13 = 0;
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v9);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
  LOBYTE(v10) = v5 != &v18;
  return (*(__int64 (__fastcall **)(char *, __int64))(*(_QWORD *)v5 + 32LL))(v5, v10);
}

```

## disassembly

```asm
0x14008ba88  mov     [rsp-8+arg_8], rbx
0x14008ba8d  mov     [rsp-8+arg_10], rsi
0x14008ba92  push    rbp
0x14008ba93  push    rdi
0x14008ba94  push    r14
0x14008ba96  lea     rbp, [rsp-20h]
0x14008ba9b  sub     rsp, 120h
0x14008baa2  mov     rax, cs:__security_cookie
0x14008baa9  xor     rax, rsp
0x14008baac  mov     [rbp+30h+var_20], rax
0x14008bab0  mov     rdi, rcx
0x14008bab3  mov     r14, [rcx+28h]
0x14008bab7  mov     rax, [rcx+38h]
0x14008babb  mov     rax, [rax+178h]
0x14008bac2  test    rax, rax
0x14008bac5  jz      short loc_14008BAD6
0x14008bac7  mov     al, [rax]
0x14008bac9  mov     [rbp+30h+var_6F], al
0x14008bacc  lea     rax, [rbp+30h+var_6F]
0x14008bad0  mov     [rbp+30h+var_68], rax
0x14008bad4  jmp     short loc_14008BADE
0x14008bad6  mov     [rbp+30h+var_68], 0
0x14008bade  lea     rax, [rsp+130h+var_F0]
0x14008bae3  mov     [rsp+130h+var_110], rax
0x14008bae8  mov     [rsp+130h+var_B8], 0
0x14008baf1  mov     rcx, [rcx+80h]
0x14008baf8  test    rcx, rcx
0x14008bafb  jz      short loc_14008BB15
0x14008bafd  mov     rax, [rcx]
0x14008bb00  lea     rdx, [rsp+130h+var_F0]
0x14008bb05  mov     rax, [rax]
0x14008bb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bb0d  mov     rcx, rax
0x14008bb10  mov     [rsp+130h+var_B8], rax
0x14008bb15  lea     rax, [rsp+130h+var_F0]
0x14008bb1a  mov     [rsp+130h+var_110], rax
0x14008bb1f  lea     rax, [rbp+30h+var_60]
0x14008bb23  mov     [rsp+130h+var_100], rax
0x14008bb28  mov     [rbp+30h+var_28], 0
0x14008bb30  test    rcx, rcx
0x14008bb33  jz      short loc_14008BB48
0x14008bb35  mov     rax, [rcx]
0x14008bb38  lea     rdx, [rbp+30h+var_60]
0x14008bb3c  mov     rax, [rax]
0x14008bb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bb44  mov     [rbp+30h+var_28], rax
0x14008bb48  mov     [rbp+30h+var_78], 0
0x14008bb50  mov     ecx, 48h ; 'H'; Size
0x14008bb55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14008bb5a  mov     rbx, rax
0x14008bb5d  mov     [rsp+130h+var_100], rax
0x14008bb62  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_96918ec15c0d1e6d6bb3c1d07c4f36b8_@@EV?$Optional@_N@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_96918ec15c0d1e6d6bb3c1d07c4f36b8_,uchar,Optional<bool>>::`vftable'
0x14008bb69  mov     [rbx], rax
0x14008bb6c  lea     rsi, [rbx+8]
0x14008bb70  mov     [rsp+130h+var_F8], rsi
0x14008bb75  mov     qword ptr [rsi+38h], 0
0x14008bb7d  mov     rcx, [rbp+30h+var_28]
0x14008bb81  test    rcx, rcx
0x14008bb84  jz      short loc_14008BB9C
0x14008bb86  mov     rax, [rcx]
0x14008bb89  mov     rdx, rsi
0x14008bb8c  mov     rax, [rax]
0x14008bb8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bb94  mov     [rsi+38h], rax
0x14008bb98  mov     rcx, [rbp+30h+var_28]
0x14008bb9c  mov     [rbp+30h+var_78], rbx
0x14008bba0  test    rcx, rcx
0x14008bba3  jz      short loc_14008BBBC
0x14008bba5  mov     rax, [rcx]
0x14008bba8  lea     rdx, [rbp+30h+var_60]
0x14008bbac  cmp     rcx, rdx
0x14008bbaf  setnz   dl
0x14008bbb2  mov     rax, [rax+20h]
0x14008bbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bbbb  nop
0x14008bbbc  mov     rcx, [rsp+130h+var_B8]
0x14008bbc1  test    rcx, rcx
0x14008bbc4  jz      short loc_14008BBE6
0x14008bbc6  mov     rax, [rcx]
0x14008bbc9  lea     rdx, [rsp+130h+var_F0]
0x14008bbce  cmp     rcx, rdx
0x14008bbd1  setnz   dl
0x14008bbd4  mov     rax, [rax+20h]
0x14008bbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bbdd  mov     [rsp+130h+var_B8], 0
0x14008bbe6  mov     rdi, [rdi+28h]
0x14008bbea  add     rdi, 160h
0x14008bbf1  mov     [rsp+130h+var_F8], rdi
0x14008bbf6  mov     rcx, rdi
0x14008bbf9  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x14008bbff  nop
0x14008bc00  mov     [rsp+130h+var_108], 0
0x14008bc09  mov     rax, [rbp+30h+var_68]
0x14008bc0d  test    rax, rax
0x14008bc10  jz      short loc_14008BC2A
0x14008bc12  mov     al, [rax]
0x14008bc14  mov     byte ptr [rsp+130h+var_110+1], al
0x14008bc18  lea     rax, [rsp+130h+var_110+1]
0x14008bc1d  mov     [rsp+130h+var_108], rax
0x14008bc22  mov     [rbp+30h+var_68], 0
0x14008bc2a  lea     rax, [rsp+130h+var_110]
0x14008bc2f  mov     [rsp+130h+var_100], rax
0x14008bc34  test    rbx, rbx
0x14008bc37  jnz     short loc_14008BC40
0x14008bc39  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14008bc3f  int     3; Trap to Debugger
0x14008bc40  mov     rax, [rbx]
0x14008bc43  lea     rdx, [rsp+130h+var_110]
0x14008bc48  mov     rcx, rbx
0x14008bc4b  mov     rax, [rax+10h]
0x14008bc4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bc54  mov     sil, al
0x14008bc57  cmp     [rsp+130h+var_108], 0
0x14008bc5d  jz      short loc_14008BC68
0x14008bc5f  mov     [rsp+130h+var_108], 0
0x14008bc68  mov     rcx, rdi
0x14008bc6b  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x14008bc71  nop
0x14008bc72  mov     dl, sil
0x14008bc75  mov     rcx, r14; this
0x14008bc78  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x14008bc7d  nop
0x14008bc7e  mov     rax, [rbx]
0x14008bc81  lea     rcx, [rbp+30h+var_B0]
0x14008bc85  cmp     rbx, rcx
0x14008bc88  setnz   dl
0x14008bc8b  mov     rcx, rbx
0x14008bc8e  mov     rax, [rax+20h]
0x14008bc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bc97  nop
0x14008bc98  mov     rcx, [rbp+30h+var_20]
0x14008bc9c  xor     rcx, rsp; StackCookie
0x14008bc9f  call    __security_check_cookie
0x14008bca4  lea     r11, [rsp+130h+var_10]
0x14008bcac  mov     rbx, [r11+28h]
0x14008bcb0  mov     rsi, [r11+30h]
0x14008bcb4  mov     rsp, r11
0x14008bcb7  pop     r14
0x14008bcb9  pop     rdi
0x14008bcba  pop     rbp
0x14008bcbb  retn
```
