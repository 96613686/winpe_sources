# std::promise<void>::~promise<void>(void)

- ea: `0x14022ba7c`
- end: `0x14022bbe6`
- name: `??1?$promise@X@std@@QEAA@XZ`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14022b9d8`

## callees

- `0x1400f4078`
- `0x1401332f0`
- `0x140133e5a`
- `0x14013785c`
- `0x14022ba50`
- `0x14022ba7c`
- `0x14022e884`
- `0x14022ea18`
- `0x14022ec70`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14022bb2a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14022bb2a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14022bb8f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14022bb8f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14022bbab`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14022bbab`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x14022bb45`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x14022bb45`

## pseudocode

```c
__int64 __fastcall std::promise<void>::~promise<void>(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int128 v5; // [rsp+20h] [rbp-49h] BYREF
  __int128 v6; // [rsp+38h] [rbp-31h] BYREF
  void **v7; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v8[16]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v9; // [rsp+60h] [rbp-9h]
  _BYTE v10[40]; // [rsp+70h] [rbp+7h] BYREF

  if ( (unsigned __int8)((__int64 (*)(void))std::_State_manager<int>::valid)()
    && (!*(_QWORD *)v2 || !*(_DWORD *)(*(_QWORD *)v2 + 188LL)) )
  {
    memset(v10, 0, sizeof(v10));
    std::logic_error::logic_error((std::logic_error *)v10, byte_140304A29);
    *(_QWORD *)v10 = &std::future_error::`vftable';
    *(_DWORD *)&v10[24] = 1;
    *(_DWORD *)&v10[28] = DWORD1(v6);
    *(_QWORD *)&v10[32] = &`std::_Immortalize_memcpy_image<std::_Future_error_category2>'::`2'::_Static;
    std::exception::exception((std::exception *)&v7, (const struct std::exception *)v10);
    v7 = &std::future_error::`vftable';
    v9 = *(_OWORD *)&v10[24];
    v5 = 0;
    __ExceptionPtrCreate(&v5);
    __ExceptionPtrCopyException(&v5, &v7, &TI3_AVfuture_error_std__);
    v7 = &std::exception::`vftable';
    o___std_exception_destroy_0(v8);
    if ( !(unsigned __int8)std::_State_manager<int>::valid(a1) )
      std::_Throw_future_error2(4);
    v3 = *a1;
    v6 = 0;
    __ExceptionPtrCopy(&v6, &v5);
    std::_Associated_state<int>::_Set_exception(v3, &v6);
    __ExceptionPtrDestroy(&v5);
    *(_QWORD *)v10 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v10[8]);
  }
  return std::_State_manager<int>::~_State_manager<int>(a1);
}

```

## disassembly

```asm
0x14022ba7c  push    rbp
0x14022ba7e  push    rbx
0x14022ba7f  push    rsi
0x14022ba80  push    rdi
0x14022ba81  lea     rbp, [rsp-3Fh]
0x14022ba86  sub     rsp, 0A8h
0x14022ba8d  mov     rax, cs:__security_cookie
0x14022ba94  xor     rax, rsp
0x14022ba97  mov     [rbp+57h+var_28], rax
0x14022ba9b  mov     rdi, rcx
0x14022ba9e  call    ?valid@?$_State_manager@H@std@@QEBA_NXZ; std::_State_manager<int>::valid(void)
0x14022baa3  test    al, al
0x14022baa5  jz      loc_14022BBC4
0x14022baab  mov     rax, [rcx]
0x14022baae  test    rax, rax
0x14022bab1  jz      short loc_14022BAC0
0x14022bab3  cmp     dword ptr [rax+0BCh], 0
0x14022baba  jnz     loc_14022BBC4
0x14022bac0  xorps   xmm0, xmm0
0x14022bac3  xor     eax, eax
0x14022bac5  movups  [rbp+57h+var_50], xmm0
0x14022bac9  movups  [rbp+57h+var_40], xmm0
0x14022bacd  mov     [rbp+57h+var_30], rax
0x14022bad1  lea     rdx, byte_140304A29; char *
0x14022bad8  lea     rcx, [rbp+57h+var_50]; this
0x14022badc  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x14022bae1  lea     rbx, ??_7future_error@std@@6B@; const std::future_error::`vftable'
0x14022bae8  mov     qword ptr [rbp+57h+var_50], rbx
0x14022baec  mov     dword ptr [rbp+57h+var_40+8], 1
0x14022baf3  mov     eax, [rbp+57h+var_84]
0x14022baf6  mov     dword ptr [rbp+57h+var_40+0Ch], eax
0x14022baf9  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_Future_error_category2@std@@@std@@YAAEBV_Future_error_category2@1@XZ@4U?$_Constexpr_immortalize_impl@V_Future_error_category2@std@@@1@A; std::_Constexpr_immortalize_impl<std::_Future_error_category2> `std::_Immortalize_memcpy_image<std::_Future_error_category2>(void)'::`2'::_Static
0x14022bb00  mov     [rbp+57h+var_30], rax
0x14022bb04  lea     rdx, [rbp+57h+var_50]; struct std::exception *
0x14022bb08  lea     rcx, [rbp+57h+var_78]; this
0x14022bb0c  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x14022bb11  mov     [rbp+57h+var_78], rbx
0x14022bb15  movups  xmm0, [rbp+57h+var_40+8]
0x14022bb19  movdqu  [rbp+57h+var_60], xmm0
0x14022bb1e  xorps   xmm1, xmm1
0x14022bb21  movdqu  [rbp+57h+var_A0], xmm1
0x14022bb26  lea     rcx, [rbp+57h+var_A0]
0x14022bb2a  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14022bb31  nop     dword ptr [rax+rax+00h]
0x14022bb36  lea     r8, _TI3?AVfuture_error@std@@; throw info for 'class std::future_error'
0x14022bb3d  lea     rdx, [rbp+57h+var_78]
0x14022bb41  lea     rcx, [rbp+57h+var_A0]
0x14022bb45  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x14022bb4c  nop     dword ptr [rax+rax+00h]
0x14022bb51  lea     rsi, ??_7exception@std@@6B@; const std::exception::`vftable'
0x14022bb58  mov     [rbp+57h+var_78], rsi
0x14022bb5c  lea     rcx, [rbp+57h+var_70]
0x14022bb60  call    _o___std_exception_destroy_0
0x14022bb65  mov     rcx, rdi
0x14022bb68  call    ?valid@?$_State_manager@H@std@@QEBA_NXZ; std::_State_manager<int>::valid(void)
0x14022bb6d  test    al, al
0x14022bb6f  jnz     short loc_14022BB7C
0x14022bb71  mov     ecx, 4
0x14022bb76  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x14022bb7c  mov     rbx, [rdi]
0x14022bb7f  xorps   xmm0, xmm0
0x14022bb82  movdqu  xmmword ptr [rbp-31h], xmm0
0x14022bb87  lea     rdx, [rbp+57h+var_A0]
0x14022bb8b  lea     rcx, [rbp+57h+var_88]
0x14022bb8f  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x14022bb96  nop     dword ptr [rax+rax+00h]
0x14022bb9b  lea     rdx, [rbp+57h+var_88]
0x14022bb9f  mov     rcx, rbx
0x14022bba2  call    ?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)
0x14022bba7  lea     rcx, [rbp+57h+var_A0]
0x14022bbab  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x14022bbb2  nop     dword ptr [rax+rax+00h]
0x14022bbb7  mov     qword ptr [rbp+57h+var_50], rsi
0x14022bbbb  lea     rcx, [rbp+57h+var_50+8]
0x14022bbbf  call    _o___std_exception_destroy_0
0x14022bbc4  mov     rcx, rdi
0x14022bbc7  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x14022bbcc  nop
0x14022bbcd  mov     rcx, [rbp+57h+var_28]
0x14022bbd1  xor     rcx, rsp; StackCookie
0x14022bbd4  call    __security_check_cookie
0x14022bbd9  add     rsp, 0A8h
0x14022bbe0  pop     rdi
0x14022bbe1  pop     rsi
0x14022bbe2  pop     rbx
0x14022bbe3  pop     rbp
0x14022bbe4  retn
```
