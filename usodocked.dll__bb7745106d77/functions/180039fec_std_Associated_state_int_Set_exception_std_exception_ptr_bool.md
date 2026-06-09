# std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x180039fec`
- end: `0x18003a0ef`
- name: `?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006bee1`

## callees

- `0x180007660`
- `0x180039fec`
- `0x18003a228`
- `0x180071010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003a086`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18003a086`
- `msvcp_win!_Mtx_unlock` at `0x18003a0b8`
- `msvcp_win!_Mtx_unlock` at `0x18003a0b8`
- `msvcp_win!_Mtx_lock` at `0x18003a022`
- `msvcp_win!_Mtx_lock` at `0x18003a022`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a031`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a04d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a031`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a04d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003a0a7`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003a0c2`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003a0a7`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003a0c2`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003a067`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18003a067`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::_Associated_state<int>::_Set_exception(__int64 a1, void *a2)
{
  __int64 v4; // rbx
  __int128 v5; // [rsp+20h] [rbp-40h] BYREF
  __int128 *v6; // [rsp+30h] [rbp-30h]
  void *v7; // [rsp+38h] [rbp-28h]
  _Mtx_t v8; // [rsp+40h] [rbp-20h] BYREF
  char v9; // [rsp+48h] [rbp-18h]

  v7 = a2;
  v4 = a1 + 32;
  v8 = (_Mtx_t)(a1 + 32);
  v9 = 0;
  if ( _Mtx_lock((_Mtx_t)(a1 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v4 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v4 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v9 = 1;
  v5 = 0;
  __ExceptionPtrCopy(&v5, a2);
  v6 = &v5;
  if ( *(_BYTE *)(a1 + 193) )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign((void *)(a1 + 16), &v5);
  (*(void (__fastcall **)(__int64, _Mtx_t *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, &v8, 0);
  __ExceptionPtrDestroy(&v5);
  if ( v9 )
    _Mtx_unlock(v8);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x180039fec  mov     [rsp-18h+arg_10], rbx
0x180039ff1  push    rbp
0x180039ff2  push    rsi
0x180039ff3  push    rdi
0x180039ff4  mov     rbp, rsp
0x180039ff7  sub     rsp, 60h
0x180039ffb  mov     rax, cs:__security_cookie
0x18003a002  xor     rax, rsp
0x18003a005  mov     [rbp+var_10], rax
0x18003a009  mov     rdi, rdx
0x18003a00c  mov     rsi, rcx
0x18003a00f  mov     [rbp+var_28], rdx
0x18003a013  lea     rbx, [rcx+20h]
0x18003a017  mov     [rbp+var_20], rbx
0x18003a01b  mov     [rbp+var_18], 0
0x18003a01f  mov     rcx, rbx; _Mtx_t
0x18003a022  call    cs:__imp__Mtx_lock
0x18003a028  test    eax, eax
0x18003a02a  jz      short loc_18003A038
0x18003a02c  mov     ecx, 5
0x18003a031  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003a037  int     3; Trap to Debugger
0x18003a038  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18003a03f  jnz     short loc_18003A054
0x18003a041  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18003a048  mov     ecx, 6
0x18003a04d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003a053  int     3; Trap to Debugger
0x18003a054  mov     [rbp+var_18], 1
0x18003a058  xorps   xmm0, xmm0
0x18003a05b  movdqu  [rbp+var_40], xmm0
0x18003a060  mov     rdx, rdi
0x18003a063  lea     rcx, [rbp+var_40]
0x18003a067  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18003a06d  lea     rax, [rbp+var_40]
0x18003a071  mov     [rbp+var_30], rax
0x18003a075  cmp     byte ptr [rsi+0C1h], 0
0x18003a07c  jnz     short loc_18003A0E4
0x18003a07e  lea     rcx, [rsi+10h]
0x18003a082  lea     rdx, [rbp+var_40]
0x18003a086  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18003a08c  mov     rax, [rsi]
0x18003a08f  xor     r8d, r8d
0x18003a092  lea     rdx, [rbp+var_20]
0x18003a096  mov     rcx, rsi
0x18003a099  mov     rax, [rax+28h]
0x18003a09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0a2  nop
0x18003a0a3  lea     rcx, [rbp+var_40]
0x18003a0a7  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003a0ad  nop
0x18003a0ae  cmp     [rbp+var_18], 0
0x18003a0b2  jz      short loc_18003A0BF
0x18003a0b4  mov     rcx, [rbp+var_20]; _Mtx_t
0x18003a0b8  call    cs:__imp__Mtx_unlock
0x18003a0be  nop
0x18003a0bf  mov     rcx, rdi
0x18003a0c2  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18003a0c8  mov     rcx, [rbp+var_10]
0x18003a0cc  xor     rcx, rsp; StackCookie
0x18003a0cf  call    __security_check_cookie
0x18003a0d4  mov     rbx, [rsp+60h+arg_10]
0x18003a0dc  add     rsp, 60h
0x18003a0e0  pop     rdi
0x18003a0e1  pop     rsi
0x18003a0e2  pop     rbp
0x18003a0e3  retn
0x18003a0e4  mov     ecx, 3
0x18003a0e9  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
